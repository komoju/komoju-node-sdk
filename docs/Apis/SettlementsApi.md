# SettlementsApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listSettlements**](SettlementsApi.md#listSettlements) | **GET** /settlements | Settlement: Index |
| [**showSettlement**](SettlementsApi.md#showSettlement) | **GET** /settlements/{id} | Settlement: Show |
| [**showSettlementCSV**](SettlementsApi.md#showSettlementCSV) | **GET** /settlements/{id}/csv | Settlement: CSV |
| [**showSettlementPDF**](SettlementsApi.md#showSettlementPDF) | **GET** /settlements/{id}/pdf | Settlement: PDF |
| [**showSettlementXLS**](SettlementsApi.md#showSettlementXLS) | **GET** /settlements/{id}/xls | Settlement: XLS |
| [**showTransaction**](SettlementsApi.md#showTransaction) | **GET** /balances/{currency}/transactions/{transaction_uuid} | Balance: Transaction |


## Setup

```typescript
import { Configuration, SettlementsApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new SettlementsApi(config);
```

## listSettlements

> SettlementList listSettlements(startTime, endTime, perPage, page)

Settlement: Index

Retrieves a paginated list of settlements from most-recent to least-recent. Pagination can be configured with `page` and `per_page` parameters.

### Example

```typescript
const result = await api.listSettlements({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
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

### Return type

[**SettlementList**](../Models/SettlementList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showSettlement

> SettlementShow showSettlement(id)

Settlement: Show

Retrieves a single settlement by its `id`, including a breakdown of payments, refunds, fees, corrections, and disbursements.

### Example

```typescript
const result = await api.showSettlement({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**SettlementShow**](../Models/SettlementShow.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showSettlementCSV

> showSettlementCSV(id)

Settlement: CSV

Retrieves the settlement in CSV format.

### Example

```typescript
const result = await api.showSettlementCSV({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

## showSettlementPDF

> showSettlementPDF(id)

Settlement: PDF

Retrieves the settlement in PDF format.

### Example

```typescript
const result = await api.showSettlementPDF({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

## showSettlementXLS

> showSettlementXLS(id)

Settlement: XLS

Retrieves the settlement in XLS format.

### Example

```typescript
const result = await api.showSettlementXLS({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

## showTransaction

> Transaction showTransaction(currency, transactionUuid)

Balance: Transaction

Retrieves a single ledger transaction by its UUID for the given currency.

### Example

```typescript
const result = await api.showTransaction({
  currency: 'YOUR_ID',
  transactionUuid: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **transactionUuid** | **String** |  | [default to null] |

### Return type

[**Transaction**](../Models/Transaction.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

