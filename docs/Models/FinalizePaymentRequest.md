# FinalizePaymentRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **capture** | **Boolean** |  | [optional] [default to null] |
| **ac\_type** | **String** | EMV chip card action code: TC (approved), AAC (declined), or fault. | [default to null] |
| **field55** | **String** | EMV tag 55 data from the chip card transaction. | [default to null] |
| **track2** | **String** | Track 2 magnetic stripe equivalent data from the chip card. | [default to null] |
| **metadata** | [**Object**](.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

