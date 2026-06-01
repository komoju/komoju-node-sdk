# Transaction

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **type** | **String** | Type of ledger transaction (e.g. \&quot;payment\&quot;, \&quot;fee\&quot;, \&quot;disbursement\&quot;). | [default to null] |
| **amount\_cents** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **happened\_at** | **Date** | Timestamp when this ledger transaction occurred. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

