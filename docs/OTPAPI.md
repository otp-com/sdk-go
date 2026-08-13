# \OTPAPI

All URIs are relative to *https://api.otp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**GetOtpStatus**](OTPAPI.md#GetOtpStatus) | **Get** /api/v1/otp/{otp_id} | Fetch the current status of an OTP.
[**ResendOtp**](OTPAPI.md#ResendOtp) | **Post** /api/v1/otp/resend | Resend a pending OTP, escalating the channel if configured.
[**SendOtp**](OTPAPI.md#SendOtp) | **Post** /api/v1/otp/send | Start an OTP: routes a channel and dispatches the code.
[**VerifyOtp**](OTPAPI.md#VerifyOtp) | **Post** /api/v1/otp/verify | Verify a code against a pending OTP.



## GetOtpStatus

> OtpStatusResponse GetOtpStatus(ctx, otpId).Execute()

Fetch the current status of an OTP.

### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/otp-com/sdk-go"
)

func main() {
	otpId := "38400000-8cf0-11bd-b23e-10b96e4ef00d" // string | 

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	resp, r, err := apiClient.OTPAPI.GetOtpStatus(context.Background(), otpId).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `OTPAPI.GetOtpStatus``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
	// response from `GetOtpStatus`: OtpStatusResponse
	fmt.Fprintf(os.Stdout, "Response from `OTPAPI.GetOtpStatus`: %v\n", resp)
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**otpId** | **string** |  | 

### Other Parameters

Other parameters are passed through a pointer to a apiGetOtpStatusRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


### Return type

[**OtpStatusResponse**](OtpStatusResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ResendOtp

> OtpResponse ResendOtp(ctx).ResendRequest(resendRequest).Execute()

Resend a pending OTP, escalating the channel if configured.

### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/otp-com/sdk-go"
)

func main() {
	resendRequest := *openapiclient.NewResendRequest("OtpId_example") // ResendRequest | 

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	resp, r, err := apiClient.OTPAPI.ResendOtp(context.Background()).ResendRequest(resendRequest).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `OTPAPI.ResendOtp``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
	// response from `ResendOtp`: OtpResponse
	fmt.Fprintf(os.Stdout, "Response from `OTPAPI.ResendOtp`: %v\n", resp)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to a apiResendOtpRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **resendRequest** | [**ResendRequest**](ResendRequest.md) |  | 

### Return type

[**OtpResponse**](OtpResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## SendOtp

> OtpResponse SendOtp(ctx).SendRequest(sendRequest).IdempotencyKey(idempotencyKey).Execute()

Start an OTP: routes a channel and dispatches the code.



### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/otp-com/sdk-go"
)

func main() {
	sendRequest := *openapiclient.NewSendRequest("+14155552671") // SendRequest | 
	idempotencyKey := "idempotencyKey_example" // string | Replay the prior response for a repeated request; a reused key with a different body is a 409. (optional)

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	resp, r, err := apiClient.OTPAPI.SendOtp(context.Background()).SendRequest(sendRequest).IdempotencyKey(idempotencyKey).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `OTPAPI.SendOtp``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
	// response from `SendOtp`: OtpResponse
	fmt.Fprintf(os.Stdout, "Response from `OTPAPI.SendOtp`: %v\n", resp)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to a apiSendOtpRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sendRequest** | [**SendRequest**](SendRequest.md) |  | 
 **idempotencyKey** | **string** | Replay the prior response for a repeated request; a reused key with a different body is a 409. | 

### Return type

[**OtpResponse**](OtpResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## VerifyOtp

> VerifyResponse VerifyOtp(ctx).VerifyRequest(verifyRequest).Execute()

Verify a code against a pending OTP.

### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/otp-com/sdk-go"
)

func main() {
	verifyRequest := *openapiclient.NewVerifyRequest("OtpId_example", "123456") // VerifyRequest | 

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	resp, r, err := apiClient.OTPAPI.VerifyOtp(context.Background()).VerifyRequest(verifyRequest).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `OTPAPI.VerifyOtp``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
	// response from `VerifyOtp`: VerifyResponse
	fmt.Fprintf(os.Stdout, "Response from `OTPAPI.VerifyOtp`: %v\n", resp)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to a apiVerifyOtpRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **verifyRequest** | [**VerifyRequest**](VerifyRequest.md) |  | 

### Return type

[**VerifyResponse**](VerifyResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

