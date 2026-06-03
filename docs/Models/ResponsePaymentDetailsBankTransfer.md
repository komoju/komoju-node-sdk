# ResponsePaymentDetailsBankTransfer

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **email** | **String** | Customer&#39;s email address. Will be used for fraud prevention, payment instruction, and payment receipt. | [default to null] |
| **order\_id** | **String** | Order identifier for this bank transfer. | [optional] [default to null] |
| **bank\_name** | **String** | Name of the bank to transfer funds to. | [optional] [default to null] |
| **account\_branch\_name** | **String** | Name of the bank branch. | [optional] [default to null] |
| **account\_number** | **String** | Bank account number to transfer funds to. | [optional] [default to null] |
| **account\_type** | **String** | Type of bank account. | [optional] [default to null] |
| **account\_name** | **String** | Name of the bank account holder. | [optional] [default to null] |
| **instructions\_url** | **String** | URL with payment instructions for the customer. | [optional] [default to null] |
| **payment\_deadline** | **Date** | Deadline by which the bank transfer must be completed. | [optional] [default to null] |
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

