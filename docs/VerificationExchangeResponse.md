# VerificationExchangeResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OtpId** | **string** | The OTP this verification belongs to. | 
**Recipient** | **string** | The recipient that was verified, in full. This is the answer the device could not be trusted to give you. | 
**RecipientType** | [**RecipientType**](RecipientType.md) |  | 
**Channel** | [**NullableChannel**](Channel.md) | Channel the verified code was delivered on. | 
**VerifiedAt** | **time.Time** | When the end user entered the correct code. | 

## Methods

### NewVerificationExchangeResponse

`func NewVerificationExchangeResponse(otpId string, recipient string, recipientType RecipientType, channel NullableChannel, verifiedAt time.Time, ) *VerificationExchangeResponse`

NewVerificationExchangeResponse instantiates a new VerificationExchangeResponse object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewVerificationExchangeResponseWithDefaults

`func NewVerificationExchangeResponseWithDefaults() *VerificationExchangeResponse`

NewVerificationExchangeResponseWithDefaults instantiates a new VerificationExchangeResponse object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetOtpId

`func (o *VerificationExchangeResponse) GetOtpId() string`

GetOtpId returns the OtpId field if non-nil, zero value otherwise.

### GetOtpIdOk

`func (o *VerificationExchangeResponse) GetOtpIdOk() (*string, bool)`

GetOtpIdOk returns a tuple with the OtpId field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetOtpId

`func (o *VerificationExchangeResponse) SetOtpId(v string)`

SetOtpId sets OtpId field to given value.


### GetRecipient

`func (o *VerificationExchangeResponse) GetRecipient() string`

GetRecipient returns the Recipient field if non-nil, zero value otherwise.

### GetRecipientOk

`func (o *VerificationExchangeResponse) GetRecipientOk() (*string, bool)`

GetRecipientOk returns a tuple with the Recipient field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetRecipient

`func (o *VerificationExchangeResponse) SetRecipient(v string)`

SetRecipient sets Recipient field to given value.


### GetRecipientType

`func (o *VerificationExchangeResponse) GetRecipientType() RecipientType`

GetRecipientType returns the RecipientType field if non-nil, zero value otherwise.

### GetRecipientTypeOk

`func (o *VerificationExchangeResponse) GetRecipientTypeOk() (*RecipientType, bool)`

GetRecipientTypeOk returns a tuple with the RecipientType field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetRecipientType

`func (o *VerificationExchangeResponse) SetRecipientType(v RecipientType)`

SetRecipientType sets RecipientType field to given value.


### GetChannel

`func (o *VerificationExchangeResponse) GetChannel() Channel`

GetChannel returns the Channel field if non-nil, zero value otherwise.

### GetChannelOk

`func (o *VerificationExchangeResponse) GetChannelOk() (*Channel, bool)`

GetChannelOk returns a tuple with the Channel field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetChannel

`func (o *VerificationExchangeResponse) SetChannel(v Channel)`

SetChannel sets Channel field to given value.


### SetChannelNil

`func (o *VerificationExchangeResponse) SetChannelNil(b bool)`

 SetChannelNil sets the value for Channel to be an explicit nil

### UnsetChannel
`func (o *VerificationExchangeResponse) UnsetChannel()`

UnsetChannel ensures that no value is present for Channel, not even an explicit nil
### GetVerifiedAt

`func (o *VerificationExchangeResponse) GetVerifiedAt() time.Time`

GetVerifiedAt returns the VerifiedAt field if non-nil, zero value otherwise.

### GetVerifiedAtOk

`func (o *VerificationExchangeResponse) GetVerifiedAtOk() (*time.Time, bool)`

GetVerifiedAtOk returns a tuple with the VerifiedAt field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetVerifiedAt

`func (o *VerificationExchangeResponse) SetVerifiedAt(v time.Time)`

SetVerifiedAt sets VerifiedAt field to given value.



[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


