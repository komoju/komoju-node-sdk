# Payment

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric payment identifier. | [default to null] |
| **resource** | **String** | Resource name. Will always be &#x60;payment&#x60;. | [default to null] |
| **status** | [**PaymentStatus**](PaymentStatus.md) |  | [default to null] |
| **amount** | **Integer** | The payment amount before tax, greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **tax** | **Integer** | The tax amount, greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **customer** | **String** | Customer UUID if associated with a customer, otherwise null. | [default to null] |
| **payment\_deadline** | **Date** | Deadline by which the payment must be completed, or null. | [default to null] |
| **payment\_details** | [**ResponsePaymentDetailsAll**](ResponsePaymentDetailsAll.md) |  | [default to null] |
| **payment\_method\_fee** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **total** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **description** | **String** | A description for this payment. May be null if it&#39;s not set. | [default to null] |
| **captured\_at** | **Date** | Timestamp when the payment was captured, or null if not yet captured. | [default to null] |
| **external\_order\_num** | **String** | Merchant-assigned external order number for this payment. | [default to null] |
| **metadata** | [**Object**](.md) | Arbitrary key-value metadata attached at payment creation time. | [default to null] |
| **created\_at** | **Date** | Timestamp when the payment was created. | [default to null] |
| **amount\_refunded** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **locale** | [**Locale**](Locale.md) |  | [default to null] |
| **session** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **customer\_family\_name** | **String** | Customer&#39;s family name. | [default to null] |
| **customer\_given\_name** | **String** | Customer&#39;s given name. | [default to null] |
| **mcc** | **String** | Merchant Category Code used for this payment. | [default to null] |
| **statement\_descriptor** | [**StatementDescriptor**](StatementDescriptor.md) |  | [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [optional] [default to null] |
| **refunds** | [**List**](Refund.md) | An array of refunds. Will be an empty array if there are no refunds. | [default to null] |
| **refund\_requests** | [**List**](RefundRequest.md) | An array of refund requests. Will be an empty array if there are no refund requests. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

