# Subscription_customer

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **Integer** | Internal numeric ID of the customer. | [default to null] |
| **uuid** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **merchant\_id** | **Integer** | Internal numeric ID of the merchant. | [default to null] |
| **created\_at** | **Date** | Timestamp when the customer was created. | [default to null] |
| **updated\_at** | **Date** | Timestamp when the customer was last updated. | [default to null] |
| **email** | **String** | Customer&#39;s email address, or null if not provided. | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **locale** | [**Locale**](Locale.md) |  | [default to null] |
| **name** | **String** | Customer-defined display name, or null if not set. | [default to null] |
| **phone** | **String** | Customer&#39;s phone number, or null if not set. | [default to null] |
| **archived\_at** | **Date** | Timestamp when the customer was archived, or null if still active. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

