# Subscription

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **resource** | **String** | Resource type name, always \&quot;subscription\&quot;. | [default to null] |
| **status** | **String** | Current status of the subscription (e.g. \&quot;active\&quot;, \&quot;cancelled\&quot;). | [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **customer** | [**Subscription_customer**](Subscription_customer.md) |  | [default to null] |
| **period** | [**SubscriptionPeriod**](SubscriptionPeriod.md) |  | [default to null] |
| **day** | **Integer** | Day of the period on which the subscription is charged. | [default to null] |
| **payment\_details** | [**Subscription_payment_details**](Subscription_payment_details.md) |  | [default to null] |
| **retry\_count** | **Integer** | Number of times payment has been retried after failure. | [default to null] |
| **retry\_at** | **Date** | Timestamp of the next scheduled payment retry, or null. | [default to null] |
| **next\_capture\_at** | **Date** | Timestamp of the next scheduled subscription charge. | [default to null] |
| **created\_at** | **Date** | Timestamp when the subscription was created. | [default to null] |
| **ended\_at** | **Date** | Timestamp when the subscription ended, or null if still active. | [default to null] |
| **metadata** | [**Object**](.md) | Arbitrary key-value metadata attached to the subscription. | [default to null] |
| **payments** | **List** | Array of payment UUIDs associated with this subscription. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

