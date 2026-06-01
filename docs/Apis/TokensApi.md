# TokensApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createToken**](TokensApi.md#createToken) | **POST** /tokens | Token: Create |


## Setup

```typescript
import { Configuration, TokensApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new TokensApi(config);
```

## createToken

> Token createToken(createTokenRequest)

Token: Create

Creates a token with the given `payment_details`.  It is recommended to have a client application make this request directly so that sensitive payment information (e.g. credit card number) doesn't hit your server. Receiving credit card numbers requires your business to be PCI-DSS compliant. Once you turn your customer's details into a token, the token string can safely be sent to your server and used as `payment_details` to a future KOMOJU API request.  A `currency` may be optionally specified. When `currency` is provided, KOMOJU will ensure that the payment made using the new token is in the same currency.

### Example

```typescript
const result = await api.createToken({
  createTokenRequest: {
    // See CreateTokenRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createTokenRequest** | [**CreateTokenRequest**](../Models/CreateTokenRequest.md) |  | |

### Return type

[**Token**](../Models/Token.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

