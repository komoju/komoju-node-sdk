# Event

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **type** | **String** | Event type slug (e.g. \&quot;payment.captured\&quot;, \&quot;payment.expired\&quot;). | [default to null] |
| **resource** | **String** | Resource type name, always \&quot;event\&quot;. | [default to null] |
| **created\_at** | **Date** | Timestamp when this event was created. | [default to null] |
| **reason** | **String** | Human-readable reason or description for this event, or null. | [default to null] |
| **data** | [**Payment**](Payment.md) |  | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

