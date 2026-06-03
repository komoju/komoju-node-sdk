# PaySessionResponse

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **redirect\_url** | **String** | URL to redirect the customer to after submitting payment details, or null if no redirect is required. | [default to null] |
| **status** | [**SessionStatus**](SessionStatus.md) |  | [default to null] |
| **payment** | [**Payment**](Payment.md) |  | [optional] [default to null] |
| **app\_url** | **String** | URL for the payment app. Only present for offsite payments with a QR/app URL. | [optional] [default to null] |
| **customer** | [**SubscriptionCustomer**](SubscriptionCustomer.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

