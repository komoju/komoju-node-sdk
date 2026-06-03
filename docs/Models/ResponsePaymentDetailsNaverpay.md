# ResponsePaymentDetailsNaverpay

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **email** | **String** | Customer&#39;s email address. Will be used for fraud prevention and payment receipt. | [default to null] |
| **callback\_url** | **String** | Callback URL used in the Naver Pay payment flow. | [optional] [default to null] |
| **mode** | **String** | Environment mode for the Naver Pay integration. | [optional] [default to null] |
| **redirect** | **Boolean** | Whether the payment uses a redirect flow. | [optional] [default to null] |
| **offsite\_fake\_new\_path** | **String** | When using test mode. | [optional] [default to null] |
| **client\_id** | **String** | Naver Pay client ID for this merchant. | [optional] [default to null] |
| **digital\_content\_only** | **Boolean** | Whether this payment is for digital content only. | [optional] [default to null] |
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

