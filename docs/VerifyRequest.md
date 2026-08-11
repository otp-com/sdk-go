# VerifyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OtpId** | **string** | The OTP id returned by send/resend. | 
**Code** | **string** | The code the recipient entered. | 

## Methods

### NewVerifyRequest

`func NewVerifyRequest(otpId string, code string, ) *VerifyRequest`

NewVerifyRequest instantiates a new VerifyRequest object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewVerifyRequestWithDefaults

`func NewVerifyRequestWithDefaults() *VerifyRequest`

NewVerifyRequestWithDefaults instantiates a new VerifyRequest object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetOtpId

`func (o *VerifyRequest) GetOtpId() string`

GetOtpId returns the OtpId field if non-nil, zero value otherwise.

### GetOtpIdOk

`func (o *VerifyRequest) GetOtpIdOk() (*string, bool)`

GetOtpIdOk returns a tuple with the OtpId field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetOtpId

`func (o *VerifyRequest) SetOtpId(v string)`

SetOtpId sets OtpId field to given value.


### GetCode

`func (o *VerifyRequest) GetCode() string`

GetCode returns the Code field if non-nil, zero value otherwise.

### GetCodeOk

`func (o *VerifyRequest) GetCodeOk() (*string, bool)`

GetCodeOk returns a tuple with the Code field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetCode

`func (o *VerifyRequest) SetCode(v string)`

SetCode sets Code field to given value.



[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


