# SecureTokensApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createSecureToken**](SecureTokensApi.md#createSecureToken) | **POST** /secure_tokens | SecureToken: Create |
| [**showSecureToken**](SecureTokensApi.md#showSecureToken) | **GET** /secure_tokens/{id} | SecureToken: Show |


## Setup

```typescript
import { Configuration, SecureTokensApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new SecureTokensApi(config);
```

## createSecureToken

> SecureToken createSecureToken(createSecureTokenRequest)

SecureToken: Create

Creates a SecureToken with the given credit card `payment_details` or `customer` ID.  There are two ways to create a SecureToken:  - Using `payment_details` with credit card information. - Using `customer` ID, which is a unique identifier for a customer created via the [Customer: Create](https://doc.komoju.com/reference/createcustomer) endpoint. Customer's saved payment details will be used as `payment_details`.  It is recommended to have a client application make this request directly so that sensitive payment information (e.g. credit card number) doesn't hit your server. Receiving credit card numbers requires your business to be PCI-DSS compliant. Once you create a secure token using a customer's credit card details, you can redirect the customer to the authentication url to perform 3DS authentication. Once a secure token has been authenticated, the secure token id can safely be sent to your server and used as `payment_details` to a future KOMOJU API request.

### Example

```typescript
const result = await api.createSecureToken({
  createSecureTokenRequest: {
    // See CreateSecureTokenRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createSecureTokenRequest** | [**CreateSecureTokenRequest**](../Models/CreateSecureTokenRequest.md) |  | |

### Return type

[**SecureToken**](../Models/SecureToken.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## showSecureToken

> SecureToken showSecureToken(id)

SecureToken: Show

Retrieves a single SecureToken object by its `id`.

### Example

```typescript
const result = await api.showSecureToken({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the SecureToken. | [default to null] |

### Return type

[**SecureToken**](../Models/SecureToken.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

