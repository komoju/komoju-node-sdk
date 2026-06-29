# OneClickApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteExternalCustomer**](OneClickApi.md#deleteExternalCustomer) | **DELETE** /external_customers/{id} | External Customer: Destroy |


## Setup

```typescript
import { Configuration, OneClickApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new OneClickApi(config);
```

## deleteExternalCustomer

> DeleteExternalCustomer_200_response deleteExternalCustomer(id)

External Customer: Destroy

Deletes the external customer created by the Hosted Page One-Click feature with the given `id`. This completely erases the stored payment details from our database.

### Example

```typescript
const result = await api.deleteExternalCustomer({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**DeleteExternalCustomer_200_response**](../Models/DeleteExternalCustomer_200_response.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

