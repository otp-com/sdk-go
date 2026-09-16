# VerificationExchangeRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**VerificationToken** | **string** | The verification_token your app received from POST /client/otp/verify. | 

## Methods

### NewVerificationExchangeRequest

`func NewVerificationExchangeRequest(verificationToken string, ) *VerificationExchangeRequest`

NewVerificationExchangeRequest instantiates a new VerificationExchangeRequest object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewVerificationExchangeRequestWithDefaults

`func NewVerificationExchangeRequestWithDefaults() *VerificationExchangeRequest`

NewVerificationExchangeRequestWithDefaults instantiates a new VerificationExchangeRequest object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetVerificationToken

`func (o *VerificationExchangeRequest) GetVerificationToken() string`

GetVerificationToken returns the VerificationToken field if non-nil, zero value otherwise.

### GetVerificationTokenOk

`func (o *VerificationExchangeRequest) GetVerificationTokenOk() (*string, bool)`

GetVerificationTokenOk returns a tuple with the VerificationToken field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetVerificationToken

`func (o *VerificationExchangeRequest) SetVerificationToken(v string)`

SetVerificationToken sets VerificationToken field to given value.



[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


