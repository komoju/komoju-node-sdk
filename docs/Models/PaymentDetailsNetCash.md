# PaymentDetailsNetCash

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type.  **Note:** This payment method support updating the payment with additional prepaid cards to cover the total balance. In case of insufficient funds, the payment status will be &#x60;pending&#x60;.  The &#x60;payment_details&#x60; in the response will also include these two attributes:  - &#x60;short_amount&#x60;: The amount that the payment is short by. - &#x60;prepaid_cards&#x60;: A list of prepaid cards used in the transaction.  Please see the integration document for more details. | [default to null] |
| **email** | **String** | Customer&#39;s email address. Will be used for fraud prevention and payment receipt. | [optional] [default to null] |
| **prepaid\_number** | **String** | Prepaid card number. | [default to null] |
| **shipping\_address\_name** | **String** | Shipping address name. This is the recipient&#39;s name. | [optional] [default to null] |
| **shipping\_address\_line1** | **String** | Shipping address line 1. | [optional] [default to null] |
| **shipping\_address\_line2** | **String** | Shipping address line 2. | [optional] [default to null] |
| **shipping\_address\_city** | **String** | Shipping address city. | [optional] [default to null] |
| **shipping\_address\_state** | **String** | Shipping address state. | [optional] [default to null] |
| **shipping\_address\_zip** | **String** | Shipping address ZIP code. | [optional] [default to null] |
| **shipping\_address\_country** | **String** | Shipping address country. | [optional] [default to null] |
| **billing\_address\_name** | **String** | Billing address name. This is the paying customer&#39;s name. | [optional] [default to null] |
| **billing\_address\_line1** | **String** | Billing address line 1. | [optional] [default to null] |
| **billing\_address\_line2** | **String** | Billing address line 2. | [optional] [default to null] |
| **billing\_address\_city** | **String** | Billing address city. | [optional] [default to null] |
| **billing\_address\_state** | **String** | Billing address state. | [optional] [default to null] |
| **billing\_address\_zip** | **String** | Billing address ZIP code. | [optional] [default to null] |
| **billing\_address\_country** | **String** | Billing address country. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

