# SessionsApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cancelSession**](SessionsApi.md#cancelSession) | **POST** /sessions/{id}/cancel | Session: Cancel |
| [**createSession**](SessionsApi.md#createSession) | **POST** /sessions | Session: Create |
| [**paySession**](SessionsApi.md#paySession) | **POST** /sessions/{id}/pay | Session: Pay |
| [**showSession**](SessionsApi.md#showSession) | **GET** /sessions/{id} | Session: Show |


## Setup

```typescript
import { Configuration, SessionsApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new SessionsApi(config);
```

## cancelSession

> Session cancelSession(id)

Session: Cancel

Cancels a session.

### Example

```typescript
const result = await api.cancelSession({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the session. | [default to null] |

### Return type

[**Session**](../Models/Session.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## createSession

> Session createSession(createSessionRequest)

Session: Create

Creates a session. There're 3 modes for the session:  * `payment`: A payment will be created after user completed the session (default). * `customer`: A customer will be created instead of a payment, or updated if `customer_id` is given. This customer resource can then be used to perform delayed billing or subscriptions. * `customer_payment`: A payment will be created, and customer will be created or updated. You can use this mode to charge money upfront and save customer's payment details in one go.

### Example

```typescript
const result = await api.createSession({
  createSessionRequest: {
    // See CreateSessionRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createSessionRequest** | [**CreateSessionRequest**](../Models/CreateSessionRequest.md) |  | |

### Return type

[**Session**](../Models/Session.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## paySession

> PaySessionResponse paySession(id, paySessionRequest)

Session: Pay

Provide customer payment details to pay for a session.

### Example

```typescript
const result = await api.paySession({
  id: 'YOUR_ID',
  paySessionRequest: {
    // See PaySessionRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the session. | [default to null] |
| **paySessionRequest** | [**PaySessionRequest**](../Models/PaySessionRequest.md) |  | |

### Return type

[**PaySessionResponse**](../Models/PaySessionResponse.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## showSession

> Session showSession(id)

Session: Show

Retrieves a Session given its ID.  A Session's status changes when the user completes or cancels their payment. You can listen for those events via webhooks, or use this API to poll for changes.

### Example

```typescript
const result = await api.showSession({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the session. | [default to null] |

### Return type

[**Session**](../Models/Session.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

