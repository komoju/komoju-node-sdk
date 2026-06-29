# ChargebacksApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**acceptChargebackRequest**](ChargebacksApi.md#acceptChargebackRequest) | **POST** /chargeback_requests/{id}/accept | Chargeback: Accept |
| [**defendChargebackRequest**](ChargebacksApi.md#defendChargebackRequest) | **POST** /chargeback_requests/{id}/defend | Chargeback: Defend |
| [**listChargebackRequests**](ChargebacksApi.md#listChargebackRequests) | **GET** /chargeback_requests | Chargeback: List |
| [**showChargebackRequest**](ChargebacksApi.md#showChargebackRequest) | **GET** /chargeback_requests/{id} | Chargeback: Show |


## Setup

```typescript
import { Configuration, ChargebacksApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new ChargebacksApi(config);
```

## acceptChargebackRequest

> acceptChargebackRequest(id)

Chargeback: Accept

Accepts a chargeback, agreeing to the dispute. Takes no request body.  A chargeback can only be accepted while its status is `pending`. If the due date has passed, the request returns an error. Accepting an already-accepted chargeback returns `204` (idempotent).

### Example

```typescript
const result = await api.acceptChargebackRequest({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | The chargeback request UUID. | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## defendChargebackRequest

> defendChargebackRequest(id, defendChargebackRequestBody)

Chargeback: Defend

Submits a defense against a chargeback, including supporting documentation.  A chargeback can only be defended while its status is `pending`. If the due date has passed, the request returns an error. Defending an already-defended chargeback returns `204` (idempotent). Only one defense can be created per chargeback request.  The `document.document_base64` payload must be 15 MB or less. Supported types are PDF, JPG/JPEG, PNG, and GIF; the type is inferred from the file's bytes, not the filename.

### Example

```typescript
const result = await api.defendChargebackRequest({
  id: 'YOUR_ID',
  defendChargebackRequestBody: {
    // See DefendChargebackRequestBody for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | The chargeback request UUID. | [default to null] |
| **defendChargebackRequestBody** | [**DefendChargebackRequestBody**](../Models/DefendChargebackRequestBody.md) |  | |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## listChargebackRequests

> ChargebackRequestList listChargebackRequests(startTime, endTime, perPage, page, status, paymentId, dueDateStart, dueDateEnd)

Chargeback: List

Retrieves a paginated list of chargeback requests for the authenticated merchant.  Results are ordered with `pending` chargebacks first, followed by non-pending chargebacks. There is no request sort parameter.  This endpoint is only available to merchants with the chargeback feature enabled; otherwise it returns `404 Not Found`.

### Example

```typescript
const result = await api.listChargebackRequests({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // status: ...,  // optional
  // paymentId: ...,  // optional
  // dueDateStart: ...,  // optional
  // dueDateEnd: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **startTime** | **Date** | Query for records created after this time. | [optional] [default to null] |
| **endTime** | **Date** | Query for records created before this time. | [optional] [default to null] |
| **perPage** | **Integer** | How many objects per page. | [optional] [default to null] |
| **page** | **Integer** | Page number to query for. | [optional] [default to null] |
| **status** | [**ChargebackStatus**](../Models/.md) | Filter by chargeback status. | [optional] [default to null] [enum: pending, accepted, cancelled, expired, defended, lost] |
| **paymentId** | **String** | Filter by the associated payment ID. | [optional] [default to null] |
| **dueDateStart** | **Date** | Lower bound (inclusive) on the chargeback&#39;s due date. | [optional] [default to null] |
| **dueDateEnd** | **Date** | Upper bound (inclusive) on the chargeback&#39;s due date. | [optional] [default to null] |

### Return type

[**ChargebackRequestList**](../Models/ChargebackRequestList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showChargebackRequest

> ChargebackRequestDetail showChargebackRequest(id)

Chargeback: Show

Retrieves the details of a single chargeback request, including its timeline, payment, customer, and defense (if one exists).  This endpoint is only available to merchants with the chargeback feature enabled; otherwise it returns `404 Not Found`.

### Example

```typescript
const result = await api.showChargebackRequest({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | The chargeback request UUID. | [default to null] |

### Return type

[**ChargebackRequestDetail**](../Models/ChargebackRequestDetail.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

