# Session

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **resource** | **String** | Resource type name, always \&quot;session\&quot;. | [default to null] |
| **mode** | [**SessionMode**](SessionMode.md) |  | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **session\_url** | **String** | URL to redirect the customer to for completing the session. | [default to null] |
| **return\_url** | **String** | URL the customer is redirected to after completing or cancelling the session. | [default to null] |
| **default\_locale** | [**Locale**](Locale.md) |  | [default to null] |
| **payment\_methods** | [**List**](PaymentMethod.md) | List of payment methods available for this session. | [default to null] |
| **created\_at** | **Date** | Timestamp when the session was created. | [default to null] |
| **cancelled\_at** | **Date** | Timestamp when the session was cancelled, or null if not cancelled. | [default to null] |
| **completed\_at** | **Date** | Timestamp when the session was completed, or null if not completed. | [default to null] |
| **status** | [**SessionStatus**](SessionStatus.md) |  | [default to null] |
| **expired** | **Boolean** | Whether the session has expired. | [default to null] |
| **merchant** | [**MerchantData**](MerchantData.md) |  | [default to null] |
| **metadata** | [**Object**](.md) | Arbitrary key-value metadata attached to this session at creation time. | [default to null] |
| **payment** | [**Payment**](Payment.md) |  | [optional] [default to null] |
| **payment\_data** | [**PaymentData**](PaymentData.md) |  | [optional] [default to null] |
| **customer\_id** | **String** | Subscription customer UUID. Only present when mode includes \&quot;customer\&quot;. | [optional] [default to null] |
| **secure\_token** | [**SecureToken**](SecureToken.md) |  | [optional] [default to null] |
| **line\_items** | [**List**](LineItem.md) | Line items for this session. Only present when line items were provided on create. | [optional] [default to null] |
| **merchant\_id** | **String** | Merchant UUID. Only present for Platform Model seller merchants. | [optional] [default to null] |
| **email** | **String** | Customer email. Only present when an email was provided. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

