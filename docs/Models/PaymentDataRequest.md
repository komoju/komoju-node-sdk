# PaymentDataRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **capture** | **String** | Whether to capture the payment automatically on completion, or hold it for manual capture later. | [optional] [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [optional] [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **external\_order\_num** | **String** | Merchant-assigned order reference number to associate with the payment. | [optional] [default to null] |
| **name** | **String** | Customer&#39;s full name. | [optional] [default to null] |
| **name\_kana** | **String** | Customer&#39;s full name in katakana. | [optional] [default to null] |
| **mcc** | **String** | Merchant Category Code to use for this payment. | [optional] [default to null] |
| **intent** | [**Intent**](Intent.md) |  | [optional] [default to null] |
| **statement\_descriptor** | [**StatementDescriptor**](StatementDescriptor.md) |  | [optional] [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [optional] [default to null] |
| **billing\_address** | [**Address**](Address.md) |  | [optional] [default to null] |
| **shipping\_address** | [**Address**](Address.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

