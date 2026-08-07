# \OTPAPI

All URIs are relative to *https://api.otp.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**GetOtpStatus**](OTPAPI.md#GetOtpStatus) | **Get** /otp/{otp_id} | Get OTP status
[**ResendOtp**](OTPAPI.md#ResendOtp) | **Post** /otp/resend | Resend an OTP
[**SendOtp**](OTPAPI.md#SendOtp) | **Post** /otp/send | Send an OTP
[**VerifyOtp**](OTPAPI.md#VerifyOtp) | **Post** /otp/verify | Verify an OTP



## GetOtpStatus

> OtpStatusResponse GetOtpStatus(ctx, otpId).Execute()

Get OTP status

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

Resend an OTP



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

Send an OTP



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
	sendRequest := *openapiclient.NewSendRequest("Recipient_example") // SendRequest | 
	idempotencyKey := "idempotencyKey_example" // string | Replays the prior response for the same key; a reused key with a different body is a 409. (optional)

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
 **idempotencyKey** | **string** | Replays the prior response for the same key; a reused key with a different body is a 409. | 

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

Verify an OTP



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
	verifyRequest := *openapiclient.NewVerifyRequest("OtpId_example", "Code_example") // VerifyRequest | 

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

