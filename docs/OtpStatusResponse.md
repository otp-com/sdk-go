# OtpStatusResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OtpId** | **string** |  | 
**Status** | [**Status**](Status.md) |  | 
**MaskedRecipient** | **string** |  | 

## Methods

### NewOtpStatusResponse

`func NewOtpStatusResponse(otpId string, status Status, maskedRecipient string, ) *OtpStatusResponse`

NewOtpStatusResponse instantiates a new OtpStatusResponse object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewOtpStatusResponseWithDefaults

`func NewOtpStatusResponseWithDefaults() *OtpStatusResponse`

NewOtpStatusResponseWithDefaults instantiates a new OtpStatusResponse object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetOtpId

`func (o *OtpStatusResponse) GetOtpId() string`

GetOtpId returns the OtpId field if non-nil, zero value otherwise.

### GetOtpIdOk

`func (o *OtpStatusResponse) GetOtpIdOk() (*string, bool)`

GetOtpIdOk returns a tuple with the OtpId field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetOtpId

`func (o *OtpStatusResponse) SetOtpId(v string)`

SetOtpId sets OtpId field to given value.


### GetStatus

`func (o *OtpStatusResponse) GetStatus() Status`

GetStatus returns the Status field if non-nil, zero value otherwise.

### GetStatusOk

`func (o *OtpStatusResponse) GetStatusOk() (*Status, bool)`

GetStatusOk returns a tuple with the Status field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetStatus

`func (o *OtpStatusResponse) SetStatus(v Status)`

SetStatus sets Status field to given value.


### GetMaskedRecipient

`func (o *OtpStatusResponse) GetMaskedRecipient() string`

GetMaskedRecipient returns the MaskedRecipient field if non-nil, zero value otherwise.

### GetMaskedRecipientOk

`func (o *OtpStatusResponse) GetMaskedRecipientOk() (*string, bool)`

GetMaskedRecipientOk returns a tuple with the MaskedRecipient field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetMaskedRecipient

`func (o *OtpStatusResponse) SetMaskedRecipient(v string)`

SetMaskedRecipient sets MaskedRecipient field to given value.



[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


