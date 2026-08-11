# ResendRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OtpId** | **string** | The OTP id to resend. | 
**Channel** | Pointer to [**NullableChannel**](Channel.md) | Move this OTP onto a specific channel, e.g. \&quot;sms\&quot; when the recipient has no WhatsApp. The channel must be enabled for your app and the recipient. Omit to advance to the next channel in your routing order. | [optional] 

## Methods

### NewResendRequest

`func NewResendRequest(otpId string, ) *ResendRequest`

NewResendRequest instantiates a new ResendRequest object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewResendRequestWithDefaults

`func NewResendRequestWithDefaults() *ResendRequest`

NewResendRequestWithDefaults instantiates a new ResendRequest object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetOtpId

`func (o *ResendRequest) GetOtpId() string`

GetOtpId returns the OtpId field if non-nil, zero value otherwise.

### GetOtpIdOk

`func (o *ResendRequest) GetOtpIdOk() (*string, bool)`

GetOtpIdOk returns a tuple with the OtpId field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetOtpId

`func (o *ResendRequest) SetOtpId(v string)`

SetOtpId sets OtpId field to given value.


### GetChannel

`func (o *ResendRequest) GetChannel() Channel`

GetChannel returns the Channel field if non-nil, zero value otherwise.

### GetChannelOk

`func (o *ResendRequest) GetChannelOk() (*Channel, bool)`

GetChannelOk returns a tuple with the Channel field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetChannel

`func (o *ResendRequest) SetChannel(v Channel)`

SetChannel sets Channel field to given value.

### HasChannel

`func (o *ResendRequest) HasChannel() bool`

HasChannel returns a boolean if a field has been set.

### SetChannelNil

`func (o *ResendRequest) SetChannelNil(b bool)`

 SetChannelNil sets the value for Channel to be an explicit nil

### UnsetChannel
`func (o *ResendRequest) UnsetChannel()`

UnsetChannel ensures that no value is present for Channel, not even an explicit nil

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


