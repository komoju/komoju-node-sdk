# BalanceTransferServiceRecord

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | The type identifier for this balance transfer record. | [default to null] |
| **recipient** | **String** | Identifier of the merchant receiving the funds. | [default to null] |
| **remitter** | **String** | Identifier of the merchant sending the funds. | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **happened\_at** | **Date** | Timestamp when the balance transfer occurred. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

