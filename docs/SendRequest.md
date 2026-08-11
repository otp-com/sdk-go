# SendRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Recipient** | **string** | Phone number (E.164) or email address to deliver the OTP to. | 
**Locale** | Pointer to **NullableString** | BCP-47 locale for the message template; falls back to the app default. | [optional] 

## Methods

### NewSendRequest

`func NewSendRequest(recipient string, ) *SendRequest`

NewSendRequest instantiates a new SendRequest object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewSendRequestWithDefaults

`func NewSendRequestWithDefaults() *SendRequest`

NewSendRequestWithDefaults instantiates a new SendRequest object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetRecipient

`func (o *SendRequest) GetRecipient() string`

GetRecipient returns the Recipient field if non-nil, zero value otherwise.

### GetRecipientOk

`func (o *SendRequest) GetRecipientOk() (*string, bool)`

GetRecipientOk returns a tuple with the Recipient field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetRecipient

`func (o *SendRequest) SetRecipient(v string)`

SetRecipient sets Recipient field to given value.


### GetLocale

`func (o *SendRequest) GetLocale() string`

GetLocale returns the Locale field if non-nil, zero value otherwise.

### GetLocaleOk

`func (o *SendRequest) GetLocaleOk() (*string, bool)`

GetLocaleOk returns a tuple with the Locale field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetLocale

`func (o *SendRequest) SetLocale(v string)`

SetLocale sets Locale field to given value.

### HasLocale

`func (o *SendRequest) HasLocale() bool`

HasLocale returns a boolean if a field has been set.

### SetLocaleNil

`func (o *SendRequest) SetLocaleNil(b bool)`

 SetLocaleNil sets the value for Locale to be an explicit nil

### UnsetLocale
`func (o *SendRequest) UnsetLocale()`

UnsetLocale ensures that no value is present for Locale, not even an explicit nil

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


