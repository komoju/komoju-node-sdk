# ResponsePaymentDetailsEpospay

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **email** | **String** | Customer&#39;s email address. Will be used for fraud prevention and payment receipt. | [default to null] |
| **offsite\_fake\_new\_path** | **String** | When using test mode. | [optional] [default to null] |
| **offsite\_url** | **String** | URL for the customer to complete the EPOS payment offsite. | [optional] [default to null] |
| **merchant\_id** | **String** | Merchant identifier used in the EPOS payment request. | [optional] [default to null] |
| **shop\_id** | **String** | Shop identifier used in the EPOS payment request. | [optional] [default to null] |
| **deal\_id** | **String** | Deal identifier for this EPOS transaction. | [optional] [default to null] |
| **token** | **String** | Authentication token for the EPOS payment. | [optional] [default to null] |
| **prd\_list** | **String** | Product list data for the EPOS payment. | [optional] [default to null] |
| **amount** | **Integer** | Payment amount in the lowest denomination of the currency. | [optional] [default to null] |
| **customer\_id** | **String** | Customer identifier in the EPOS system. | [optional] [default to null] |
| **return\_url** | **String** | URL to redirect the customer to after completing the EPOS payment. | [optional] [default to null] |
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

