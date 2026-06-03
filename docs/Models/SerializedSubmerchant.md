# SerializedSubmerchant

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | Unique identifier for this sub-merchant. | [default to null] |
| **live** | **Boolean** | Whether this merchant is operating in live (production) mode. | [default to null] |
| **created\_at** | **Date** | Timestamp when this merchant was created. | [default to null] |
| **updated\_at** | **Date** | Timestamp when this merchant record was last updated. | [default to null] |
| **account\_id** | **String** | Account identifier associated with this merchant. | [default to null] |
| **name** | **String** | Display name of the sub-merchant. | [default to null] |
| **platform\_role** | [**MerchantRole**](MerchantRole.md) |  | [default to null] |
| **status** | **String** | Current account/application status of the merchant. | [default to null] |
| **payments\_enabled** | **Boolean** | Whether payments are currently enabled for this merchant. | [default to null] |
| **payouts\_enabled** | **Boolean** | Whether payouts are currently enabled for this merchant. | [default to null] |
| **send\_payment\_instruction\_email** | **Boolean** | Whether payment instruction emails are sent to customers for this merchant. | [default to null] |
| **send\_payment\_receipt\_email** | **Boolean** | Whether payment receipt emails are sent to customers for this merchant. | [default to null] |
| **send\_payment\_reminder\_email** | **Boolean** | Whether payment reminder emails are sent to customers for this merchant. | [default to null] |
| **send\_payment\_refund\_email** | **Boolean** | Whether refund notification emails are sent to customers for this merchant. | [default to null] |
| **expiry\_settings** | [**List**](SerializedSubmerchant_expiry_settings_inner.md) |  | [default to null] |
| **active\_payment\_methods** | [**List**](SerializedSubmerchant_active_payment_methods_inner.md) |  | [default to null] |
| **publishable\_key** | **String** | The merchant&#39;s publishable API key for client-side use. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

