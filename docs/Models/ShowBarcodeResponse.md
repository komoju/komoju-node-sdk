# ShowBarcodeResponse

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **status** | **String** | Barcode is available | [default to null] |
| **retry\_after** | **Integer** | Request may be retried after specified amount of seconds | [default to null] |
| **expires\_at** | **Date** | Barcode cannot be used for payment after this time | [default to null] |
| **image** | **String** | Base64 encoded PNG image (width: 750px, height: 150px). This value can be used as the &#x60;src&#x60; attribute of an HTML &#x60;&lt;img&gt;&#x60; tag. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

