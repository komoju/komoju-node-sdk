# PlatformPayment

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **resource** | **String** | Resource type name, always \&quot;payment\&quot;. | [default to null] |
| **status** | [**PaymentStatus**](PaymentStatus.md) |  | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **tax** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **customer** | **String** | Customer UUID if associated with a customer, otherwise null. | [default to null] |
| **payment\_deadline** | **String** | Deadline by which the payment must be completed, or null. | [default to null] |
| **payment\_details** | **String** | Serialized payment method details for this payment. | [default to null] |
| **payment\_method\_fee** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **total** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **description** | **String** | Optional description for the payment. | [default to null] |
| **captured\_at** | **Date** | Timestamp when the payment was captured, or null if not yet captured. | [default to null] |
| **external\_order\_num** | **String** | External order reference from the merchant&#39;s system. | [default to null] |
| **metadata** | [**Object**](.md) | Arbitrary key-value metadata attached to the payment. | [default to null] |
| **created\_at** | **Date** | Timestamp when the payment was created. | [default to null] |
| **amount\_refunded** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **locale** | [**Locale**](Locale.md) |  | [default to null] |
| **session** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **customer\_family\_name** | **String** | Customer&#39;s family name. | [default to null] |
| **customer\_given\_name** | **String** | Customer&#39;s given name. | [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [default to null] |
| **mcc** | **String** | Merchant Category Code used for this payment. | [default to null] |
| **statement\_descriptor** | **String** | Statement descriptor shown to the customer on their bank statement. | [default to null] |
| **refunds** | **List** | Array of refund objects associated with this payment. | [default to null] |
| **refund\_requests** | **List** | Array of refund request objects associated with this payment. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

