# Refund

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric refund identifier. | [default to null] |
| **resource** | **String** | Resource name. Will always be &#x60;refund&#x60;. | [default to null] |
| **amount** | **Integer** | The refund amount with tax included, greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **payment** | **String** | A unique 25-character alphanumeric payment identifier. | [default to null] |
| **description** | **String** | Description of the refund. | [default to null] |
| **created\_at** | **Date** |  | [default to null] |
| **chargeback** | **Boolean** | Denotes if this refund was created due to a chargeback. | [default to null] |
| **refund\_type** | **String** |  | [optional] [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

