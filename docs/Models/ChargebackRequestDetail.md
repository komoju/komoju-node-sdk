# ChargebackRequestDetail

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **status** | [**ChargebackStatus**](ChargebackStatus.md) |  | [default to null] |
| **reason\_code** | **String** | Machine-readable reason code. Internal codes (e.g. \&quot;CB_Fraud\&quot;) are used by default; for Worldpay Visa/Mastercard payments the network&#39;s own reason codes are used instead (e.g. \&quot;10.4\&quot; or \&quot;4837\&quot;). | [default to null] |
| **reason** | **String** | Human-readable chargeback reason corresponding to the reason code. | [default to null] |
| **created\_at** | **Date** | Timestamp when the chargeback was created. | [default to null] |
| **due\_date** | **Date** | Deadline by which the merchant must respond. | [default to null] |
| **last\_updated\_at** | **Date** | Timestamp when the chargeback was last updated. | [default to null] |
| **timeline** | [**List**](ChargebackTimelineEntry.md) | Chronological list of chargeback events. | [default to null] |
| **payment** | [**ChargebackPayment**](ChargebackPayment.md) |  | [default to null] |
| **customer** | [**ChargebackCustomer**](ChargebackCustomer.md) |  | [default to null] |
| **defense** | [**ChargebackDefense**](ChargebackDefense.md) |  | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

