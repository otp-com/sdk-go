# ErrorBody

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** | Machine-readable error class, e.g. \&quot;OtpNotFoundError\&quot;. | 
**Message** | **string** | Human-readable message. Safe to log; never contains the OTP code. | 
**Details** | Pointer to **map[string]interface{}** | Structured context, present on validation errors ({loc, msg, type} per field) and a few domain errors. | [optional] 

## Methods

### NewErrorBody

`func NewErrorBody(type_ string, message string, ) *ErrorBody`

NewErrorBody instantiates a new ErrorBody object
This constructor will assign default values to properties that have it defined,
and makes sure properties required by API are set, but the set of arguments
will change when the set of required properties is changed

### NewErrorBodyWithDefaults

`func NewErrorBodyWithDefaults() *ErrorBody`

NewErrorBodyWithDefaults instantiates a new ErrorBody object
This constructor will only assign default values to properties that have it defined,
but it doesn't guarantee that properties required by API are set

### GetType

`func (o *ErrorBody) GetType() string`

GetType returns the Type field if non-nil, zero value otherwise.

### GetTypeOk

`func (o *ErrorBody) GetTypeOk() (*string, bool)`

GetTypeOk returns a tuple with the Type field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetType

`func (o *ErrorBody) SetType(v string)`

SetType sets Type field to given value.


### GetMessage

`func (o *ErrorBody) GetMessage() string`

GetMessage returns the Message field if non-nil, zero value otherwise.

### GetMessageOk

`func (o *ErrorBody) GetMessageOk() (*string, bool)`

GetMessageOk returns a tuple with the Message field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetMessage

`func (o *ErrorBody) SetMessage(v string)`

SetMessage sets Message field to given value.


### GetDetails

`func (o *ErrorBody) GetDetails() map[string]interface{}`

GetDetails returns the Details field if non-nil, zero value otherwise.

### GetDetailsOk

`func (o *ErrorBody) GetDetailsOk() (*map[string]interface{}, bool)`

GetDetailsOk returns a tuple with the Details field if it's non-nil, zero value otherwise
and a boolean to check if the value has been set.

### SetDetails

`func (o *ErrorBody) SetDetails(v map[string]interface{})`

SetDetails sets Details field to given value.

### HasDetails

`func (o *ErrorBody) HasDetails() bool`

HasDetails returns a boolean if a field has been set.


[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


