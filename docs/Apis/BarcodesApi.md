# BarcodesApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**showBarcode**](BarcodesApi.md#showBarcode) | **GET** /barcodes/{payment_id} | Barcode: Show |


## Setup

```typescript
import { Configuration, BarcodesApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new BarcodesApi(config);
```

## showBarcode

> ShowBarcodeResponse showBarcode(paymentId)

Barcode: Show

Fetches the latest barcode for a konbini payment.  Barcodes can be displayed in your client application to give your customers a more convenient way to pay. Not all konbini payments are compatible with barcodes. If a payment is compatible, it will have a `barcode_url` field in its `payment_details` object, which is a reference to this endpoint.  Newly created payments may not have a barcode available immediately. If the barcode is still being generated, the response will have a `status` of `pending` and a `retry_after` field indicating how many seconds to wait before you may retry the request.  The barcodes can only be used for payment for a limited amount of time, by default this is 10 minutes. Subsequent requests to this endpoint will return the same barcode as long as it is still valid. After expiration, a new barcode will be generated and returned.  <details> <summary>Fetching barcodes in JavaScript</summary>  If you're integrating barcodes on your website, the following JavaScript function can be used to fetch barcode data, handling the pending status and retrying. The `barcode_url` parameter is returned from Payments APIs when the payment is compatible with barcodes.  ```javascript async function fetchBarcode(barcode_url) {   const response = await fetch(barcode_url);   if (!response.ok) {     throw new Error(       `Error fetching barcode: ${response.status} ${response.statusText}`     );   }    const { status, retry_after, ...barcode } = await response.json();   if (status === 'ready') {     return barcode;   } else if (status === 'pending') {     await new Promise(resolve => setTimeout(resolve, retry_after * 1000));     return fetchBarcode(barcode_url);   } else {     throw new Error(`Error fetching barcode: unexpected status ${status}`);   } } ``` </details>

### Example

```typescript
const result = await api.showBarcode({
  paymentId: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **paymentId** | **String** | Payment unique identifier | [default to null] |

### Return type

[**ShowBarcodeResponse**](../Models/ShowBarcodeResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

