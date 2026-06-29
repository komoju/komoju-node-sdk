# ChargebackPayment

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **created\_at** | **Date** | Timestamp when the payment was created. | [default to null] |
| **captured\_at** | **Date** | Timestamp when the payment was captured, or null. | [default to null] |
| **payment\_method** | [**ChargebackPaymentMethod**](ChargebackPaymentMethod.md) |  | [default to null] |
| **masked\_card\_number** | **String** | Masked card number, or null if not applicable. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

