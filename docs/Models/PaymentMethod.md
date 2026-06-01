# PaymentMethod

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Machine-readable type slug for this payment method (e.g. \&quot;credit_card\&quot;, \&quot;konbini\&quot;). | [default to null] |
| **hashed\_gateway** | **String** | Hashed identifier of the payment gateway processing this method. | [optional] [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [optional] [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **exchange\_rate** | **Float** | Exchange rate applied when this payment method&#39;s currency differs from the session currency. | [optional] [default to null] |
| **offsite** | **Boolean** | Whether this payment method redirects the customer to an external site to complete payment. | [optional] [default to null] |
| **additional\_fields** | **List** | Names of additional input fields required to complete payment with this method. | [optional] [default to null] |
| **brands** | [**PaymentMethod_brands**](PaymentMethod_brands.md) |  | [optional] [default to null] |
| **seven\_eleven\_merchant\_number** | **String** | Only for Konbini | [optional] [default to null] |
| **installments** | [**List**](PaymentMethod_installments_inner.md) | Only for Komoju Pay | [optional] [default to null] |
| **api\_endpoint** | **String** | Only for Komoju Pay | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

