# DisbursementsApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cancelDisbursement**](DisbursementsApi.md#cancelDisbursement) | **POST** /disbursements/{id}/cancel | Disbursement: Cancel |
| [**createDisbursement**](DisbursementsApi.md#createDisbursement) | **POST** /disbursements | Disbursement: Create |
| [**disbursementReport**](DisbursementsApi.md#disbursementReport) | **GET** /disbursements/report | Disbursement: Report |
| [**listDisbursements**](DisbursementsApi.md#listDisbursements) | **GET** /disbursements | Disbursement: List |
| [**showDisbursement**](DisbursementsApi.md#showDisbursement) | **GET** /disbursements/{id} | Disbursement: Show |


## Setup

```typescript
import { Configuration, DisbursementsApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new DisbursementsApi(config);
```

## cancelDisbursement

> Disbursement cancelDisbursement(id, cancelDisbursementRequest)

Disbursement: Cancel

Cancels a disbursement.

### Example

```typescript
const result = await api.cancelDisbursement({
  id: 'YOUR_ID',
  cancelDisbursementRequest: {
    // See CancelDisbursementRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |
| **cancelDisbursementRequest** | [**CancelDisbursementRequest**](../Models/CancelDisbursementRequest.md) |  | |

### Return type

[**Disbursement**](../Models/Disbursement.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createDisbursement

> Disbursement createDisbursement(createDisbursementRequest)

Disbursement: Create

Creates a new disbursement.

### Example

```typescript
const result = await api.createDisbursement({
  createDisbursementRequest: {
    // See CreateDisbursementRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createDisbursementRequest** | [**CreateDisbursementRequest**](../Models/CreateDisbursementRequest.md) |  | |

### Return type

[**Disbursement**](../Models/Disbursement.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## disbursementReport

> disbursementReport(startTime, endTime, currency, status)

Disbursement: Report

View disbursements in CSV format.

### Example

```typescript
const result = await api.disbursementReport({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // currency: ...,  // optional
  // status: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **startTime** | **Date** |  | [default to null] |
| **endTime** | **Date** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **status** | [**DisbursementStatus**](../Models/.md) |  | [default to null] [enum: pending, paid, failed, cancelled] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listDisbursements

> DisbursementList listDisbursements(startTime, endTime, perPage, page, currency)

Disbursement: List

Lists disbursements.

### Example

```typescript
const result = await api.listDisbursements({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // currency: ...,  // optional
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
| **currency** | [**Currency**](../Models/.md) |  | [optional] [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |

### Return type

[**DisbursementList**](../Models/DisbursementList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showDisbursement

> Disbursement showDisbursement(id)

Disbursement: Show

Retrieves a disbursement.

### Example

```typescript
const result = await api.showDisbursement({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**Disbursement**](../Models/Disbursement.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

