# CreateRefundRequestRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **amount** | **Integer** | The payment amount before tax, greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **customer\_name** | **String** | Customer&#39;s name in half-width katakana, as registered at the bank. | [default to null] |
| **bank\_name** | **String** | Name of the customer&#39;s bank. | [default to null] |
| **bank\_code** | **String** | Optional 4-digit Zengin bank code. | [optional] [default to null] |
| **branch\_name** | **String** | Name of the customer&#39;s bank branch. | [optional] [default to null] |
| **branch\_number** | **String** | 3-digit branch number. | [default to null] |
| **account\_type** | **String** | Type of the customer&#39;s bank account. | [default to null] |
| **account\_number** | **Integer** | 7-digit bank account number to deposit the refund into. | [default to null] |
| **include\_payment\_method\_fee** | **Boolean** | Whether the refund should include the original payment method fee. | [default to null] |
| **description** | **String** | Optional description or reason for this refund request. | [optional] [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

