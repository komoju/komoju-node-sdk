# CreateSecureTokenRequestWithCustomer

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **customer** | **String** | To use instead of &#x60;payment_details&#x60;, specify customer&#39;s identifier for this SecureToken.  This identifier can be obtained from [Customer: Create](https://doc.komoju.com/reference/createcustomer) endpoint. | [default to null] |
| **return\_url** | **String** |  | [default to null] |
| **platform\_details** | [**ProcessingMerchant**](ProcessingMerchant.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

