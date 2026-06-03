# CreateSubscriptionRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **customer** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **period** | [**SubscriptionPeriod**](SubscriptionPeriod.md) |  | [default to null] |
| **metadata** | [**Object**](.md) | Store any additional data you want to associate with the subscription. The object&#39;s keys and values must be strings. Keys have a maximum length of 30 characters. Values have a maximum length of 2000 characters. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

