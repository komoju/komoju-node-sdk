# Disbursement

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **fee** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **fee\_tax** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **status** | [**DisbursementStatus**](DisbursementStatus.md) |  | [default to null] |
| **bank\_code** | **String** | 4-digit Zengin bank code of the recipient&#39;s bank. | [default to null] |
| **branch\_code** | **String** | 3-digit Zengin branch code. | [default to null] |
| **account\_type** | **String** | Type of the recipient&#39;s bank account. | [default to null] |
| **account\_number** | **String** | Recipient&#39;s bank account number. | [default to null] |
| **account\_name\_kana** | **String** | Name of the recipient bank account holder in katakana. | [default to null] |
| **error** | **String** | Error message if the disbursement failed, otherwise null. | [default to null] |
| **external\_id** | **String** | Merchant-assigned external reference ID for this disbursement. | [default to null] |
| **created\_at** | **Date** | Timestamp when the disbursement was created. | [default to null] |
| **last\_updated\_at** | **Date** | Timestamp when the disbursement record was last updated. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

