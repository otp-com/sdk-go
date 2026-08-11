# OtpResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OtpId** | **string** |  | 
**Status** | [**Status**](Status.md) |  | 
**Channel** | [**NullableChannel**](Channel.md) | Channel the OTP was dispatched on; null until routed. | 
**MaskedRecipient** | **string** | Recipient with the middle digits masked. | 
**ActionUrl** | Pointer to **NullableString** | WhatsApp link the user opens to receive the code: they send us the prefilled message and we reply with the code over WhatsApp, then they enter it and you call POST /otp/verify. Present only when dispatched on the whatsapp channel; null otherwise. | [optional] 

## Methods

### NewOtpResponse

`func NewOtpResponse(otpId string, status Status, channel NullableChannel, maskedRecipient string, ) *OtpResponse`

NewOtpResponse instantiates a new OtpResponse object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewOtpResponseWithDefaults

`func NewOtpResponseWithDefaults() *OtpResponse`

NewOtpResponseWithDefaults instantiates a new OtpResponse object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetOtpId

`func (o *OtpResponse) GetOtpId() string`

GetOtpId returns the OtpId field if non-nil, zero value otherwise.

### GetOtpIdOk

`func (o *OtpResponse) GetOtpIdOk() (*string, bool)`

GetOtpIdOk returns a tuple with the OtpId field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetOtpId

`func (o *OtpResponse) SetOtpId(v string)`

SetOtpId sets OtpId field to given value.


### GetStatus

`func (o *OtpResponse) GetStatus() Status`

GetStatus returns the Status field if non-nil, zero value otherwise.

### GetStatusOk

`func (o *OtpResponse) GetStatusOk() (*Status, bool)`

GetStatusOk returns a tuple with the Status field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetStatus

`func (o *OtpResponse) SetStatus(v Status)`

SetStatus sets Status field to given value.


### GetChannel

`func (o *OtpResponse) GetChannel() Channel`

GetChannel returns the Channel field if non-nil, zero value otherwise.

### GetChannelOk

`func (o *OtpResponse) GetChannelOk() (*Channel, bool)`

GetChannelOk returns a tuple with the Channel field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetChannel

`func (o *OtpResponse) SetChannel(v Channel)`

SetChannel sets Channel field to given value.


### SetChannelNil

`func (o *OtpResponse) SetChannelNil(b bool)`

 SetChannelNil sets the value for Channel to be an explicit nil

### UnsetChannel
`func (o *OtpResponse) UnsetChannel()`

UnsetChannel ensures that no value is present for Channel, not even an explicit nil
### GetMaskedRecipient

`func (o *OtpResponse) GetMaskedRecipient() string`

GetMaskedRecipient returns the MaskedRecipient field if non-nil, zero value otherwise.

### GetMaskedRecipientOk

`func (o *OtpResponse) GetMaskedRecipientOk() (*string, bool)`

GetMaskedRecipientOk returns a tuple with the MaskedRecipient field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetMaskedRecipient

`func (o *OtpResponse) SetMaskedRecipient(v string)`

SetMaskedRecipient sets MaskedRecipient field to given value.


### GetActionUrl

`func (o *OtpResponse) GetActionUrl() string`

GetActionUrl returns the ActionUrl field if non-nil, zero value otherwise.

### GetActionUrlOk

`func (o *OtpResponse) GetActionUrlOk() (*string, bool)`

GetActionUrlOk returns a tuple with the ActionUrl field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetActionUrl

`func (o *OtpResponse) SetActionUrl(v string)`

SetActionUrl sets ActionUrl field to given value.

### HasActionUrl

`func (o *OtpResponse) HasActionUrl() bool`

HasActionUrl returns a boolean if a field has been set.

### SetActionUrlNil

`func (o *OtpResponse) SetActionUrlNil(b bool)`

 SetActionUrlNil sets the value for ActionUrl to be an explicit nil

### UnsetActionUrl
`func (o *OtpResponse) UnsetActionUrl()`

UnsetActionUrl ensures that no value is present for ActionUrl, not even an explicit nil

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


