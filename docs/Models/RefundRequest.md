# RefundRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric refund request identifier. | [default to null] |
| **payment** | **String** | A unique 25-character alphanumeric payment identifier. | [default to null] |
| **customer\_name** | **String** | Customer&#39;s name in half-width katakana characters. | [default to null] |
| **bank\_name** | **String** | The name of the bank that customer would like money to be deposited to. | [default to null] |
| **bank\_code** | **String** | 4-digit bank code. May be &#x60;null&#x60; if it&#39;s not given. | [default to null] |
| **branch\_name** | **String** | The name of the branch. | [default to null] |
| **branch\_number** | **String** | 3-digit branch number. | [default to null] |
| **account\_number** | **String** | 7-digit account number. | [default to null] |
| **description** | **String** | Optional description or reason for this refund request. | [optional] [default to null] |
| **status** | [**RefundRequestStatus**](RefundRequestStatus.md) |  | [default to null] |
| **created\_at** | **Date** | Timestamp when the refund request was created. | [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

