# Customer

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **resource** | **String** | Resource type name, always \&quot;customer\&quot;. | [default to null] |
| **email** | **String** | Customer&#39;s email address, or null if not provided. | [default to null] |
| **source** | [**Customer_source**](Customer_source.md) |  | [default to null] |
| **metadata** | [**Object**](.md) | Arbitrary key-value metadata attached to this customer. | [default to null] |
| **created\_at** | **Date** | Timestamp when the customer was created. | [default to null] |
| **locale** | [**Locale**](Locale.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

