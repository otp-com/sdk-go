# \VerificationsAPI

All URIs are relative to *https://api.otp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**ExchangeVerification**](VerificationsAPI.md#ExchangeVerification) | **Post** /api/v1/verifications/exchange | Exchange a verification token for the recipient it proves.



## ExchangeVerification

> VerificationExchangeResponse ExchangeVerification(ctx).VerificationExchangeRequest(verificationExchangeRequest).Execute()

Exchange a verification token for the recipient it proves.



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
	verificationExchangeRequest := *openapiclient.NewVerificationExchangeRequest("otp_vt_3xZ9kQ2m7pLw42mN8kaB3xZ9kQ2m7pLw") // VerificationExchangeRequest | 

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	resp, r, err := apiClient.VerificationsAPI.ExchangeVerification(context.Background()).VerificationExchangeRequest(verificationExchangeRequest).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `VerificationsAPI.ExchangeVerification``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
	// response from `ExchangeVerification`: VerificationExchangeResponse
	fmt.Fprintf(os.Stdout, "Response from `VerificationsAPI.ExchangeVerification`: %v\n", resp)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to a apiExchangeVerificationRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **verificationExchangeRequest** | [**VerificationExchangeRequest**](VerificationExchangeRequest.md) |  | 

### Return type

[**VerificationExchangeResponse**](VerificationExchangeResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

