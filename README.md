# otp.com Go SDK

Go client for the [otp.com](https://otp.com) OTP API: send a one-time password, verify the code the
user entered, resend it on another channel.

Requires Go 1.23+.

- **API contract:** [otp-com/sdk](https://github.com/otp-com/sdk) (`openapi.yaml`)
- **Method and model reference:** [`docs/`](./docs)
- **Other languages:** [Node.js](https://github.com/otp-com/sdk-node) ·
  [PHP](https://github.com/otp-com/sdk-php) · [Python](https://github.com/otp-com/sdk-python) ·
  [MCP server](https://github.com/otp-com/mcp)

## Install

Installed straight from GitHub; Go has no separate package registry to publish to.

```sh
go get github.com/otp-com/sdk-go@latest
```

There is no version tag yet, so `@latest` resolves to a pseudo-version of the `main` branch
(`v0.0.0-<date>-<commit>`). That is what lands in your `go.mod`, and `go.sum` pins the exact commit,
so builds stay reproducible. To pick a specific commit or branch yourself:

```sh
go get github.com/otp-com/sdk-go@<commit-sha>
go get github.com/otp-com/sdk-go@main
```

Once the repository is tagged, switch to `go get github.com/otp-com/sdk-go@v1.0.0`.

## Quickstart

Get an API key from the otp.com panel under **API Keys**. `otp_live_…` sends for real, `otp_test_…`
runs in sandbox. Keep it server-side; it is a bearer credential.

The key travels on the context, so one client can serve several keys.

```go
package main

import (
	"context"
	"log"
	"os"

	otp "github.com/otp-com/sdk-go"
)

func main() {
	client := otp.NewAPIClient(otp.NewConfiguration())
	ctx := context.WithValue(context.Background(), otp.ContextAccessToken, os.Getenv("OTP_API_KEY"))

	// 1. Send. You pass the recipient; your account routing picks the channel.
	// SetClientIp = the END USER's IP from your request context, not your server's:
	// requests without it share a much tighter rate limit.
	req := otp.NewSendRequest("+14155552671")
	req.SetLocale("en")
	req.SetClientIp("81.2.69.142")

	sent, _, err := client.OTPAPI.SendOtp(ctx).SendRequest(*req).Execute()
	if err != nil {
		log.Fatal(err)
	}

	sent.GetOtpId()           // keep this: you verify against it
	sent.GetChannel()         // "sms" | "whatsapp" | "email" | "telegram"
	sent.GetMaskedRecipient() // "+14****71", safe to show the user
	sent.GetActionUrl()       // WhatsApp only, see below

	// 2. Verify whatever the user typed in.
	result, _, err := client.OTPAPI.VerifyOtp(ctx).
		VerifyRequest(*otp.NewVerifyRequest(sent.GetOtpId(), "123456")).
		Execute()
	if err != nil {
		log.Fatal(err)
	}

	if result.GetMatched() {
		// The code was correct; result.GetStatus() is "approved".
	}
}
```

The code itself is never returned by the API. `recipient` is a phone number in E.164 or an email
address; which one is valid depends on the channels enabled for your app.

Every call returns `(payload, *http.Response, error)`. The middle value is the raw response, useful
for logging status codes and request IDs.

### Retries that must not double-send

Pass an idempotency key and a repeat of the same call replays the first response instead of sending
a second code. Reusing a key with a different body is a `409`.

```go
sent, _, err := client.OTPAPI.SendOtp(ctx).
	SendRequest(*otp.NewSendRequest(recipient)).
	IdempotencyKey("signup:" + userID).
	Execute()
```

## WhatsApp: the code comes back to the user

Verification is identical on every channel, but WhatsApp delivery has one extra step. When routing
picks WhatsApp, the code has **not** been sent yet and the response carries an action URL:

```go
if url, ok := sent.GetActionUrlOk(); ok {
	// Open it for the user. They send us the prefilled message from their own WhatsApp,
	// we reply with the code, and the OTP stays "pending" until they enter it.
	redirect(*url)
}
```

Then call `VerifyOtp` exactly as on SMS. The action URL is null on every other channel. Don't poll
for a WhatsApp OTP to approve itself: nothing leaves `pending` without a `VerifyOtp` call. If the
user has no WhatsApp, resend on a channel they do have.

## Resending

```go
// Advance to the next channel in your routing order.
resend := otp.NewResendRequest(sent.GetOtpId())
_, _, err := client.OTPAPI.ResendOtp(ctx).ResendRequest(*resend).Execute()

// Or move it onto a specific channel, e.g. the user has no WhatsApp.
resend.SetChannel("sms")
_, _, err = client.OTPAPI.ResendOtp(ctx).ResendRequest(*resend).Execute()
```

A resend before the cooldown elapses is a `429`; a channel that isn't enabled for your app or the
recipient is a `409`.

## Checking status

```go
current, _, err := client.OTPAPI.GetOtpStatus(ctx, sent.GetOtpId()).Execute()
current.GetStatus() // "pending" | "approved" | "failed" | "expired"
```

Useful for reconciliation and support tooling. It is not a substitute for `VerifyOtp`, which is what
actually approves an OTP.

## Errors

Any non-2xx response returns a `*otp.GenericOpenAPIError` alongside the raw `*http.Response`. The
body is always `{"error": {"type", "message", "details"?}}`, where `type` is a stable
machine-readable class.

```go
sent, resp, err := client.OTPAPI.SendOtp(ctx).SendRequest(*req).Execute()
if err != nil {
	var apiErr *otp.GenericOpenAPIError
	if errors.As(err, &apiErr) {
		log.Printf("status=%d body=%s", resp.StatusCode, apiErr.Body())
	}
	return err
}
```

| Status | When |
| --- | --- |
| `401` | Missing or invalid API key, disabled app, or suspended company |
| `404` | Unknown `otp_id` (also returned for another company's OTP, to avoid probing) |
| `409` | No enabled channel, channel not enabled, resend not allowed, or idempotency-key conflict |
| `422` | Request body failed validation |
| `429` | Resend cooldown has not elapsed |

## Configuration

```go
cfg := otp.NewConfiguration()
cfg.Servers = otp.ServerConfigurations{{URL: "https://api.otp.com/api/v1"}} // default
cfg.HTTPClient = &http.Client{Timeout: 10 * time.Second}
cfg.AddDefaultHeader("X-Request-Id", requestID)

client := otp.NewAPIClient(cfg)
```

`otp.NewAPIClient` is safe for concurrent use; build one and share it.

## API reference

| Method | Endpoint | Returns |
| --- | --- | --- |
| [`SendOtp`](./docs/OTPAPI.md#sendotp) | `POST /otp/send` | [`OtpResponse`](./docs/OtpResponse.md) |
| [`VerifyOtp`](./docs/OTPAPI.md#verifyotp) | `POST /otp/verify` | [`VerifyResponse`](./docs/VerifyResponse.md) |
| [`ResendOtp`](./docs/OTPAPI.md#resendotp) | `POST /otp/resend` | [`OtpResponse`](./docs/OtpResponse.md) |
| [`GetOtpStatus`](./docs/OTPAPI.md#getotpstatus) | `GET /otp/{otp_id}` | [`OtpStatusResponse`](./docs/OtpStatusResponse.md) |

Optional fields use the `Nullable*` wrappers: `GetX()` returns the zero value when unset,
`GetXOk()` tells you whether it was actually present.

## Regenerating

Everything in this repo except this README is generated from
[`openapi.yaml`](https://github.com/otp-com/sdk) by
[OpenAPI Generator](https://openapi-generator.tech). Fix the contract, not the `.go` files; a pull
request against generated files will be overwritten by the next regeneration.

- **In CI:** run the **Regenerate from spec** workflow, or let `otp-com/sdk` dispatch it.
- **Locally:** `./update-sdk.sh sdk-go` from a checkout of `otp-com/sdk`.

`README.md` is listed in `.openapi-generator-ignore` so it survives regeneration. When the contract
changes, update it by hand.

## License

MIT
