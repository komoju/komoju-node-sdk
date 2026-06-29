# PlatformModelApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**balanceTransfer**](PlatformModelApi.md#balanceTransfer) | **POST** /balances/{currency}/transfer | Balance: Transfer |
| [**createFile**](PlatformModelApi.md#createFile) | **POST** /merchants/{merchant_id}/files | File: Create |
| [**createMerchant**](PlatformModelApi.md#createMerchant) | **POST** /merchants | Merchant: Create |
| [**createMerchantBalanceTransfer**](PlatformModelApi.md#createMerchantBalanceTransfer) | **POST** /merchants/{merchant_id}/balances/{currency}/transfer | Balance: Transfer |
| [**editMerchantBalanceSettings**](PlatformModelApi.md#editMerchantBalanceSettings) | **PUT** /merchants/{merchant_id}/balances/{currency}/settings | Balances: Edit Settings |
| [**listLiveApplicationPaymentMethods**](PlatformModelApi.md#listLiveApplicationPaymentMethods) | **GET** /live_application/{merchant_id}/payment_methods | Live Application: Payment Methods |
| [**listMerchants**](PlatformModelApi.md#listMerchants) | **GET** /merchants | Merchant: List |
| [**listSubmerchantPayments**](PlatformModelApi.md#listSubmerchantPayments) | **GET** /merchants/{merchant_id}/payments | Payment: List for Merchant |
| [**listSubmerchantSettlements**](PlatformModelApi.md#listSubmerchantSettlements) | **GET** /merchants/{merchant_id}/settlements | Settlement: List |
| [**merchantBalanceTransactions**](PlatformModelApi.md#merchantBalanceTransactions) | **GET** /merchants/{merchant_id}/balances/{currency}/transactions | Balance: Transactions |
| [**showFile**](PlatformModelApi.md#showFile) | **GET** /merchants/{merchant_id}/files/{id} | File: Show |
| [**showLiveApplication**](PlatformModelApi.md#showLiveApplication) | **GET** /live_application/{merchant_id} | Live Application: Show |
| [**showLiveApplicationPaymentMethod**](PlatformModelApi.md#showLiveApplicationPaymentMethod) | **GET** /live_application/{merchant_id}/payment_methods/{payment_method} | Live Application: Show Payment Method |
| [**showMerchant**](PlatformModelApi.md#showMerchant) | **GET** /merchants/{id} | Merchant: Show |
| [**showMerchantBalance**](PlatformModelApi.md#showMerchantBalance) | **GET** /merchants/{merchant_id}/balances/{currency} | Balance: Show |
| [**showMerchantBalanceSettings**](PlatformModelApi.md#showMerchantBalanceSettings) | **GET** /merchants/{merchant_id}/balances/{currency}/settings | Balance: Show Settings |
| [**showMerchantBalanceTransaction**](PlatformModelApi.md#showMerchantBalanceTransaction) | **GET** /merchants/{merchant_id}/balances/{currency}/transactions/{transaction_uuid} | Balance: Transaction |
| [**showSubmerchantSettlement**](PlatformModelApi.md#showSubmerchantSettlement) | **GET** /merchants/{merchant_id}/settlements/{id} | Settlement: Show |
| [**simulateLiveApplicationPaymentMethodStatus**](PlatformModelApi.md#simulateLiveApplicationPaymentMethodStatus) | **PATCH** /live_application/{merchant_id}/payment_methods/{payment_method}/simulate_status | Live Application: Simulate Payment Method Status |
| [**simulateLiveApplicationStatus**](PlatformModelApi.md#simulateLiveApplicationStatus) | **PATCH** /live_application/{merchant_id}/simulate_status | Live Application: Simulate Status |
| [**submerchantSettlementCSV**](PlatformModelApi.md#submerchantSettlementCSV) | **GET** /merchants/{merchant_id}/settlements/{id}/csv | Settlement: CSV |
| [**submerchantSettlementPDF**](PlatformModelApi.md#submerchantSettlementPDF) | **GET** /merchants/{merchant_id}/settlements/{id}/pdf | Settlement: PDF |
| [**submerchantSettlementXLS**](PlatformModelApi.md#submerchantSettlementXLS) | **GET** /merchants/{merchant_id}/settlements/{id}/xls | Settlement: XLS |
| [**updateLiveApplication**](PlatformModelApi.md#updateLiveApplication) | **PATCH** /live_application/{merchant_id} | Live Application: Update |
| [**updateLiveApplicationPaymentMethod**](PlatformModelApi.md#updateLiveApplicationPaymentMethod) | **PATCH** /live_application/{merchant_id}/payment_methods/{payment_method} | Live Application: Update Payment Method |
| [**updateMerchant**](PlatformModelApi.md#updateMerchant) | **PATCH** /merchants/{id} | Merchant: Update |


## Setup

```typescript
import { Configuration, PlatformModelApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new PlatformModelApi(config);
```

## balanceTransfer

> Transfer balanceTransfer(currency, balanceTransferRequest)

Balance: Transfer

Transfers funds from the currently authenticated merchant's balance to another associated merchant for the given `currency`.

### Example

```typescript
const result = await api.balanceTransfer({
  currency: 'YOUR_ID',
  balanceTransferRequest: {
    // See BalanceTransferRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **balanceTransferRequest** | [**BalanceTransferRequest**](../Models/BalanceTransferRequest.md) |  | |

### Return type

[**Transfer**](../Models/Transfer.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createFile

> MerchantFile createFile(merchantId, createFileRequest)

File: Create

Creates a new file for the current merchant.

### Example

```typescript
const result = await api.createFile({
  merchantId: 'YOUR_ID',
  createFileRequest: {
    // See CreateFileRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **createFileRequest** | [**CreateFileRequest**](../Models/CreateFileRequest.md) |  | |

### Return type

[**MerchantFile**](../Models/MerchantFile.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createMerchant

> SerializedSubmerchant createMerchant(createMerchantRequest)

Merchant: Create

Creates a new merchant.

### Example

```typescript
const result = await api.createMerchant({
  createMerchantRequest: {
    // See CreateMerchantRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createMerchantRequest** | [**CreateMerchantRequest**](../Models/CreateMerchantRequest.md) |  | |

### Return type

[**SerializedSubmerchant**](../Models/SerializedSubmerchant.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createMerchantBalanceTransfer

> BalanceTransferServiceRecord createMerchantBalanceTransfer(merchantId, currency, createMerchantBalanceTransferRequest)

Balance: Transfer

Creates a balance transfer between associated merchants for a given `amount` and `currency`.

### Example

```typescript
const result = await api.createMerchantBalanceTransfer({
  merchantId: 'YOUR_ID',
  currency: 'YOUR_ID',
  createMerchantBalanceTransferRequest: {
    // See CreateMerchantBalanceTransferRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **createMerchantBalanceTransferRequest** | [**CreateMerchantBalanceTransferRequest**](../Models/CreateMerchantBalanceTransferRequest.md) |  | |

### Return type

[**BalanceTransferServiceRecord**](../Models/BalanceTransferServiceRecord.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## editMerchantBalanceSettings

> MerchantBalance editMerchantBalanceSettings(merchantId, currency, editMerchantBalanceSettingsRequest)

Balances: Edit Settings

Given a currency, edit the payout settings of the currently authenticated merchant or one of its sub-merchants.

### Example

```typescript
const result = await api.editMerchantBalanceSettings({
  merchantId: 'YOUR_ID',
  currency: 'YOUR_ID',
  editMerchantBalanceSettingsRequest: {
    // See EditMerchantBalanceSettingsRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **editMerchantBalanceSettingsRequest** | [**EditMerchantBalanceSettingsRequest**](../Models/EditMerchantBalanceSettingsRequest.md) |  | |

### Return type

[**MerchantBalance**](../Models/MerchantBalance.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## listLiveApplicationPaymentMethods

> PaymentMethodsList listLiveApplicationPaymentMethods(merchantId, locale)

Live Application: Payment Methods

List submitted/unsubmitted payment methods

### Example

```typescript
const result = await api.listLiveApplicationPaymentMethods({
  merchantId: 'YOUR_ID',
  // locale: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **locale** | [**Locale**](../Models/.md) |  | [optional] [default to null] [enum: ja, en, ko] |

### Return type

[**PaymentMethodsList**](../Models/PaymentMethodsList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listMerchants

> SubmerchantsList listMerchants(startTime, endTime, perPage, page, live, platformRole, status, paymentsEnabled, payoutsEnabled)

Merchant: List

Retrieves a paginated list of sub-merchants. Results can be filtered by `live` status, `platform_role`, account `status`, and whether payments or payouts are enabled.

### Example

```typescript
const result = await api.listMerchants({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // live: ...,  // optional
  // platformRole: ...,  // optional
  // status: ...,  // optional
  // paymentsEnabled: ...,  // optional
  // payoutsEnabled: ...,  // optional
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
| **live** | **Boolean** |  | [optional] [default to null] |
| **platformRole** | [**MerchantRole**](../Models/.md) |  | [optional] [default to null] [enum: seller, payout] |
| **status** | **String** |  | [optional] [default to null] |
| **paymentsEnabled** | **Boolean** |  | [optional] [default to null] |
| **payoutsEnabled** | **Boolean** |  | [optional] [default to null] |

### Return type

[**SubmerchantsList**](../Models/SubmerchantsList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listSubmerchantPayments

> PlatformMerchantPaymentList listSubmerchantPayments(merchantId, startTime, endTime, perPage, page, currency, externalOrderNum, status)

Payment: List for Merchant

Retrieves a paginated list of payments. Pagination can be configured with `page` and `per_page` parameters.  Payments can be filtered by `currency`, `external_order_num`, and `status`.  A time range can be specified with `start_time`, and `end_time`.

### Example

```typescript
const result = await api.listSubmerchantPayments({
  merchantId: 'YOUR_ID',
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // currency: ...,  // optional
  // externalOrderNum: ...,  // optional
  // status: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **startTime** | **Date** | Query for records created after this time. | [optional] [default to null] |
| **endTime** | **Date** | Query for records created before this time. | [optional] [default to null] |
| **perPage** | **Integer** | How many objects per page. | [optional] [default to null] |
| **page** | **Integer** | Page number to query for. | [optional] [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [optional] [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **externalOrderNum** | **String** |  | [optional] [default to null] |
| **status** | [**PaymentStatus**](../Models/.md) |  | [optional] [default to null] [enum: pending, authorized, captured, cancelled, expired, refunded, failed] |

### Return type

[**PlatformMerchantPaymentList**](../Models/PlatformMerchantPaymentList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listSubmerchantSettlements

> SettlementList listSubmerchantSettlements(merchantId)

Settlement: List

Lists out past settlements from most-recent to least-recent.

### Example

```typescript
const result = await api.listSubmerchantSettlements({
  merchantId: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |

### Return type

[**SettlementList**](../Models/SettlementList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## merchantBalanceTransactions

> BalanceTransactionList merchantBalanceTransactions(merchantId, currency, startTime, endTime, perPage, page, type)

Balance: Transactions

Given a currency, view the ledger transactions of the currently authenticated merchant or one of its sub-merchants. Will split ledger transactions into line items when appropriate.

### Example

```typescript
const result = await api.merchantBalanceTransactions({
  merchantId: 'YOUR_ID',
  currency: 'YOUR_ID',
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // type: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **startTime** | **Date** | Query for records created after this time. | [optional] [default to null] |
| **endTime** | **Date** | Query for records created before this time. | [optional] [default to null] |
| **perPage** | **Integer** | How many objects per page. | [optional] [default to null] |
| **page** | **Integer** | Page number to query for. | [optional] [default to null] |
| **type** | **String** |  | [optional] [default to null] |

### Return type

[**BalanceTransactionList**](../Models/BalanceTransactionList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showFile

> MerchantFile showFile(merchantId, id)

File: Show

Retrieves an existing file of the current merchant.

### Example

```typescript
const result = await api.showFile({
  merchantId: 'YOUR_ID',
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **id** | **String** |  | [default to null] |

### Return type

[**MerchantFile**](../Models/MerchantFile.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showLiveApplication

> LiveApplicationWithSubmittedFields showLiveApplication(merchantId, locale)

Live Application: Show

Shows the live application status of the applicant merchant

### Example

```typescript
const result = await api.showLiveApplication({
  merchantId: 'YOUR_ID',
  // locale: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **locale** | [**Locale**](../Models/.md) |  | [optional] [default to null] [enum: ja, en, ko] |

### Return type

[**LiveApplicationWithSubmittedFields**](../Models/LiveApplicationWithSubmittedFields.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showLiveApplicationPaymentMethod

> PaymentMethodApplicationWithSubmittedFields showLiveApplicationPaymentMethod(merchantId, paymentMethod, locale)

Live Application: Show Payment Method

Shows the payment method status of the applicant merchant

### Example

```typescript
const result = await api.showLiveApplicationPaymentMethod({
  merchantId: 'YOUR_ID',
  paymentMethod: 'YOUR_ID',
  // locale: ...,  // optional
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **paymentMethod** | **String** |  | [default to null] |
| **locale** | [**Locale**](../Models/.md) |  | [optional] [default to null] [enum: ja, en, ko] |

### Return type

[**PaymentMethodApplicationWithSubmittedFields**](../Models/PaymentMethodApplicationWithSubmittedFields.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showMerchant

> SerializedSubmerchant showMerchant(id)

Merchant: Show

Retrieves the details of a sub-merchant by its `id`, including account settings, payout configuration, and live status.

### Example

```typescript
const result = await api.showMerchant({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**SerializedSubmerchant**](../Models/SerializedSubmerchant.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showMerchantBalance

> BalanceShow showMerchantBalance(merchantId, currency)

Balance: Show

Given a currency, view the unsettled balance of the currently authenticated merchant or one of its sub-merchants.

### Example

```typescript
const result = await api.showMerchantBalance({
  merchantId: 'YOUR_ID',
  currency: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |

### Return type

[**BalanceShow**](../Models/BalanceShow.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showMerchantBalanceSettings

> BalanceSettings showMerchantBalanceSettings(merchantId, currency)

Balance: Show Settings

Given a currency, view the payout settings of the currently authenticated merchant or one of its sub-merchants.

### Example

```typescript
const result = await api.showMerchantBalanceSettings({
  merchantId: 'YOUR_ID',
  currency: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |

### Return type

[**BalanceSettings**](../Models/BalanceSettings.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showMerchantBalanceTransaction

> List showMerchantBalanceTransaction(merchantId, currency, transactionUuid)

Balance: Transaction

Given a currency and a transaction UUID, view the corresponding ledger transaction of the currently authenticated merchant or one of its sub-merchants. Will return one entry per line item of the transaction.

### Example

```typescript
const result = await api.showMerchantBalanceTransaction({
  merchantId: 'YOUR_ID',
  currency: 'YOUR_ID',
  transactionUuid: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **transactionUuid** | **String** |  | [default to null] |

### Return type

[**List**](../Models/Transaction.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showSubmerchantSettlement

> SettlementShow showSubmerchantSettlement(merchantId, id)

Settlement: Show

View a settlement given an `id`.

### Example

```typescript
const result = await api.showSubmerchantSettlement({
  merchantId: 'YOUR_ID',
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **id** | **String** |  | [default to null] |

### Return type

[**SettlementShow**](../Models/SettlementShow.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## simulateLiveApplicationPaymentMethodStatus

> PaymentMethodStatus simulateLiveApplicationPaymentMethodStatus(merchantId, paymentMethod, simulateLiveApplicationPaymentMethodStatusRequest)

Live Application: Simulate Payment Method Status

Simulate status change on payment method for test merchants

### Example

```typescript
const result = await api.simulateLiveApplicationPaymentMethodStatus({
  merchantId: 'YOUR_ID',
  paymentMethod: 'YOUR_ID',
  simulateLiveApplicationPaymentMethodStatusRequest: {
    // See SimulateLiveApplicationPaymentMethodStatusRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **paymentMethod** | **String** |  | [default to null] |
| **simulateLiveApplicationPaymentMethodStatusRequest** | [**SimulateLiveApplicationPaymentMethodStatusRequest**](../Models/SimulateLiveApplicationPaymentMethodStatusRequest.md) |  | |

### Return type

[**PaymentMethodStatus**](../Models/PaymentMethodStatus.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## simulateLiveApplicationStatus

> MerchantSubmissionStatus simulateLiveApplicationStatus(merchantId, simulateLiveApplicationPaymentMethodStatusRequest)

Live Application: Simulate Status

Simulate status change on applications for test merchants. In order for status to be changed to \"accepted,\" at least one payment method must be approved.

### Example

```typescript
const result = await api.simulateLiveApplicationStatus({
  merchantId: 'YOUR_ID',
  simulateLiveApplicationPaymentMethodStatusRequest: {
    // See SimulateLiveApplicationPaymentMethodStatusRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **simulateLiveApplicationPaymentMethodStatusRequest** | [**SimulateLiveApplicationPaymentMethodStatusRequest**](../Models/SimulateLiveApplicationPaymentMethodStatusRequest.md) |  | |

### Return type

[**MerchantSubmissionStatus**](../Models/MerchantSubmissionStatus.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## submerchantSettlementCSV

> submerchantSettlementCSV(merchantId, id)

Settlement: CSV

View a settlement in CSV format given an `id`.

### Example

```typescript
const result = await api.submerchantSettlementCSV({
  merchantId: 'YOUR_ID',
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **id** | **String** |  | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

## submerchantSettlementPDF

> submerchantSettlementPDF(merchantId, id)

Settlement: PDF

View a settlement in PDF format given an `id`.

### Example

```typescript
const result = await api.submerchantSettlementPDF({
  merchantId: 'YOUR_ID',
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **id** | **String** |  | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

## submerchantSettlementXLS

> submerchantSettlementXLS(merchantId, id)

Settlement: XLS

View a settlement in XLS format given an `id`.

### Example

```typescript
const result = await api.submerchantSettlementXLS({
  merchantId: 'YOUR_ID',
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **id** | **String** |  | [default to null] |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

## updateLiveApplication

> LiveApplication updateLiveApplication(merchantId, liveApplicationRequest)

Live Application: Update

Updates the live application for the applicant merchant

### Example

```typescript
const result = await api.updateLiveApplication({
  merchantId: 'YOUR_ID',
  liveApplicationRequest: {
    // See LiveApplicationRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **liveApplicationRequest** | [**LiveApplicationRequest**](../Models/LiveApplicationRequest.md) |  | |

### Return type

[**LiveApplication**](../Models/LiveApplication.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## updateLiveApplicationPaymentMethod

> PaymentMethodApplication updateLiveApplicationPaymentMethod(merchantId, paymentMethod, updatePaymentMethodRequest)

Live Application: Update Payment Method

Update the payment method application of the applicant merchant

### Example

```typescript
const result = await api.updateLiveApplicationPaymentMethod({
  merchantId: 'YOUR_ID',
  paymentMethod: 'YOUR_ID',
  updatePaymentMethodRequest: {
    // See UpdatePaymentMethodRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **String** |  | [default to null] |
| **paymentMethod** | **String** |  | [default to null] |
| **updatePaymentMethodRequest** | [**UpdatePaymentMethodRequest**](../Models/UpdatePaymentMethodRequest.md) |  | |

### Return type

[**PaymentMethodApplication**](../Models/PaymentMethodApplication.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## updateMerchant

> SerializedSubmerchant updateMerchant(id, updateMerchantRequest)

Merchant: Update

Updates a sub-merchant's settings, including payment and payout toggles, email notification preferences, and payment method expiry settings.

### Example

```typescript
const result = await api.updateMerchant({
  id: 'YOUR_ID',
  updateMerchantRequest: {
    // See UpdateMerchantRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |
| **updateMerchantRequest** | [**UpdateMerchantRequest**](../Models/UpdateMerchantRequest.md) |  | |

### Return type

[**SerializedSubmerchant**](../Models/SerializedSubmerchant.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

