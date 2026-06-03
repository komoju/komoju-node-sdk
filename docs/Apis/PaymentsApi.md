# PaymentsApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cancelPayment**](PaymentsApi.md#cancelPayment) | **POST** /payments/{id}/cancel | Payment: Cancel |
| [**capturePayment**](PaymentsApi.md#capturePayment) | **POST** /payments/{id}/capture | Payment: Capture |
| [**createPayment**](PaymentsApi.md#createPayment) | **POST** /payments | Payment: Create |
| [**createRefundRequest**](PaymentsApi.md#createRefundRequest) | **POST** /payments/{id}/refund_request | Payment: Refund Request |
| [**finalizePayment**](PaymentsApi.md#finalizePayment) | **POST** /payments/{id}/finalize | Payment: Finalize |
| [**listPaymentMethods**](PaymentsApi.md#listPaymentMethods) | **GET** /payment_methods | Payment Method: List |
| [**listPayments**](PaymentsApi.md#listPayments) | **GET** /payments | Payment: List |
| [**refundPayment**](PaymentsApi.md#refundPayment) | **POST** /payments/{id}/refund | Payment: Refund |
| [**showPayment**](PaymentsApi.md#showPayment) | **GET** /payments/{id} | Payment: Show |
| [**updatePayment**](PaymentsApi.md#updatePayment) | **PATCH** /payments/{id} | Payment: Update |


## Setup

```typescript
import { Configuration, PaymentsApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new PaymentsApi(config);
```

## cancelPayment

> Payment cancelPayment(id)

Payment: Cancel

Cancels a payment.  The given payment must have a state of `pending` or `authorized` in order to be canceled.

### Example

```typescript
const result = await api.cancelPayment({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## capturePayment

> Payment capturePayment(id, capturePaymentRequest)

Payment: Capture

Captures a payment.  Only works when the payment was created with `capture` set to false, or via a session with `capture` set to `\"manual\"`.

### Example

```typescript
const result = await api.capturePayment({
  id: 'YOUR_ID',
  capturePaymentRequest: {
    // See CapturePaymentRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |
| **capturePaymentRequest** | [**CapturePaymentRequest**](../Models/CapturePaymentRequest.md) |  | |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createPayment

> Payment createPayment(createPaymentRequest)

Payment: Create

Creates a payment for a given `amount` and `currency`.  There are two ways to create payment:  - For one-time payment, you can pass `payment_details` with payment method type and additional attributes. - For recurring payment, you can pass customer's ID via `customer` attribute. Customer's saved payment method will be used for the payment.  Note that either `payment_details` or `customer` is required for the payment. However, both of them should not be given at the same time.

### Example

```typescript
const result = await api.createPayment({
  createPaymentRequest: {
    // See CreatePaymentRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createPaymentRequest** | [**CreatePaymentRequest**](../Models/CreatePaymentRequest.md) |  | |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createRefundRequest

> createRefundRequest(id, createRefundRequestRequest)

Payment: Refund Request

A \"Refund Request\" requests that a payment be refunded manually. This can be used for payment methods that do not support refunds, such as konbini. To support non-refundable payment methods, a bank account must be specified so that we know where to send the funds. Since it is a manual process, the refund will be carried out at a later date, and there's a possibility of it being rejected.

### Example

```typescript
const result = await api.createRefundRequest({
  id: 'YOUR_ID',
  createRefundRequestRequest: {
    // See CreateRefundRequestRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |
| **createRefundRequestRequest** | [**CreateRefundRequestRequest**](../Models/CreateRefundRequestRequest.md) |  | |

### Return type

null (empty response body)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## finalizePayment

> Payment finalizePayment(id, finalizePaymentRequest)

Payment: Finalize

Finalizes a payment.  Finalizes an EMV contact transaction by confirming the chip card's final decision (TC for approved, AAC for declined). Use this after authorization to submit the terminal's transaction outcome and determine whether the payment is captured or cancelled.

### Example

```typescript
const result = await api.finalizePayment({
  id: 'YOUR_ID',
  finalizePaymentRequest: {
    // See FinalizePaymentRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |
| **finalizePaymentRequest** | [**FinalizePaymentRequest**](../Models/FinalizePaymentRequest.md) |  | |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## listPaymentMethods

> List listPaymentMethods()

Payment Method: List

Lists available payment methods.

### Example

```typescript
const result = await api.listPaymentMethods();
console.log(result.data);
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**List**](../Models/AvailablePaymentMethod.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listPayments

> PaymentList listPayments(startTime, endTime, perPage, page, merchantId, currency, externalOrderNum, status)

Payment: List

Retrieves a paginated list of payments. Pagination can be configured with `page` and `per_page` parameters.  Payments can be filtered by `currency`, `external_order_num`, and `status`.  A time range can be specified with `start_time`, and `end_time`.

### Example

```typescript
const result = await api.listPayments({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // merchantId: ...,  // optional
  // currency: ...,  // optional
  // externalOrderNum: ...,  // optional
  // status: ...,  // optional
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
| **merchantId** | **String** |  | [optional] [default to null] |
| **currency** | [**Currency**](../Models/.md) |  | [optional] [default to null] [enum: JPY, USD, EUR, TWD, KRW, PLN, GBP, HKD, SGD, NZD, AUD, IDR, MYR, PHP, THB, CNY, BRL, CHF, CAD, VND] |
| **externalOrderNum** | **String** | A unique ID from your application used to track this payment. | [optional] [default to null] |
| **status** | **String** | The status of the payment. Can be a single status or comma-separated values. | [optional] [default to null] |

### Return type

[**PaymentList**](../Models/PaymentList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## refundPayment

> Payment refundPayment(id, refundPaymentRequest)

Payment: Refund

Refunds an arbitrary amount of money from an existing payment. If no amount is specified, the whole payment is refunded.

### Example

```typescript
const result = await api.refundPayment({
  id: 'YOUR_ID',
  refundPaymentRequest: {
    // See RefundPaymentRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |
| **refundPaymentRequest** | [**RefundPaymentRequest**](../Models/RefundPaymentRequest.md) |  | |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## showPayment

> Payment showPayment(id)

Payment: Show

Retrieves a single payment object by its `id`.

### Example

```typescript
const result = await api.showPayment({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## updatePayment

> Payment updatePayment(id, updatePaymentRequest)

Payment: Update

Updates a payment.  Only a payment's `description` and `metadata` can be changed.

### Example

```typescript
const result = await api.updatePayment({
  id: 'YOUR_ID',
  updatePaymentRequest: {
    // See UpdatePaymentRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for the payment. | [default to null] |
| **updatePaymentRequest** | [**UpdatePaymentRequest**](../Models/UpdatePaymentRequest.md) |  | |

### Return type

[**Payment**](../Models/Payment.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

