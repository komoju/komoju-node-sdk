# PaymentMethodApplicationWithSubmittedFields

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **merchant\_id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **status** | [**PaymentMethodApplicationStatus**](PaymentMethodApplicationStatus.md) |  | [default to null] |
| **payments\_enabled** | **Boolean** | Whether payments have been enabled following payment-method review. | [default to null] |
| **payouts\_enabled** | **Boolean** | Whether payouts have been enabled following payment-method review. | [default to null] |
| **requested\_fields** | [**List**](Field.md) | Fields currently required to be submitted for this payment method. | [default to null] |
| **newly\_requested\_fields** | [**List**](Field.md) | Fields newly added to the required list since last submission. | [default to null] |
| **errored\_fields** | [**List**](ErroredField.md) | Fields that were submitted but failed validation. | [default to null] |
| **submitted\_fields** | [**List**](SubmittedField.md) |  | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

