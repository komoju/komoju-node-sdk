# SubscriptionsApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCustomer**](SubscriptionsApi.md#createCustomer) | **POST** /customers | Customer: Create |
| [**createSubscription**](SubscriptionsApi.md#createSubscription) | **POST** /subscriptions | Subscription: Create |
| [**deleteCustomer**](SubscriptionsApi.md#deleteCustomer) | **DELETE** /customers/{id} | Customer: Destroy |
| [**deleteSubscription**](SubscriptionsApi.md#deleteSubscription) | **DELETE** /subscriptions/{id} | Subscription: Destroy |
| [**listCustomers**](SubscriptionsApi.md#listCustomers) | **GET** /customers | Customer: List |
| [**listSubscriptions**](SubscriptionsApi.md#listSubscriptions) | **GET** /subscriptions | Subscription: List |
| [**showCustomer**](SubscriptionsApi.md#showCustomer) | **GET** /customers/{id} | Customer: Show |
| [**showSubscription**](SubscriptionsApi.md#showSubscription) | **GET** /subscriptions/{id} | Subscription: Show |
| [**updateCustomer**](SubscriptionsApi.md#updateCustomer) | **PATCH** /customers/{id} | Customer: Update |


## Setup

```typescript
import { Configuration, SubscriptionsApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new SubscriptionsApi(config);
```

## createCustomer

> Customer createCustomer(createCustomerRequest)

Customer: Create

Creates a new customer with the specified `payment_details`. Customer payment details are stored in a secure, PCI DSS-compliant way.  Once you have a customer, you may specify the customer's `id` instead of `payment_details` when creating a payment.

### Example

```typescript
const result = await api.createCustomer({
  createCustomerRequest: {
    // See CreateCustomerRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createCustomerRequest** | [**CreateCustomerRequest**](../Models/CreateCustomerRequest.md) |  | |

### Return type

[**Customer**](../Models/Customer.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## createSubscription

> Subscription createSubscription(createSubscriptionRequest)

Subscription: Create

Create a new subscription. A subscription represents a recurring payment. Recurring payments may be on a `weekly`, `monthly`, or `yearly` basis, specified by the period parameter.  In order to create a subscription, a customer ID must be supplied. The customer object contains saved payment info, which is regularly charged by the subscription.  A subscription can't be modified once it's created. To change a subscription, you must delete it and create a new one.

### Example

```typescript
const result = await api.createSubscription({
  createSubscriptionRequest: {
    // See CreateSubscriptionRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **createSubscriptionRequest** | [**CreateSubscriptionRequest**](../Models/CreateSubscriptionRequest.md) |  | |

### Return type

[**Subscription**](../Models/Subscription.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

## deleteCustomer

> Customer deleteCustomer(id)

Customer: Destroy

Deletes the customer with the given `id`. This complete erases the stored payment details from our database.

### Example

```typescript
const result = await api.deleteCustomer({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**Customer**](../Models/Customer.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## deleteSubscription

> Subscription deleteSubscription(id)

Subscription: Destroy

Delete a subscription. Once deleted, the subscription's regular payments will stop.

### Example

```typescript
const result = await api.deleteSubscription({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**Subscription**](../Models/Subscription.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listCustomers

> CustomerList listCustomers(startTime, endTime, perPage, page, expiration)

Customer: List

Retrieves a paginated list of all previously-registered customers.

### Example

```typescript
const result = await api.listCustomers({
  // startTime: ...,  // optional
  // endTime: ...,  // optional
  // perPage: ...,  // optional
  // page: ...,  // optional
  // expiration: ...,  // optional
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
| **expiration** | **String** | The expiration of the customer&#39;s credit card in MMYY format. | [optional] [default to null] |

### Return type

[**CustomerList**](../Models/CustomerList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## listSubscriptions

> SubscriptionList listSubscriptions(startTime, endTime, perPage, page)

Subscription: List

List existing subscriptions.

### Example

```typescript
const result = await api.listSubscriptions({
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

[**SubscriptionList**](../Models/SubscriptionList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showCustomer

> Customer showCustomer(id)

Customer: Show

Retrieves customer personal information.

### Example

```typescript
const result = await api.showCustomer({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**Customer**](../Models/Customer.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showSubscription

> Subscription showSubscription(id)

Subscription: Show

Show an existing subscription, including its customer and scrubbed payment details.

### Example

```typescript
const result = await api.showSubscription({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |

### Return type

[**Subscription**](../Models/Subscription.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## updateCustomer

> Customer updateCustomer(id, updateCustomerRequest)

Customer: Update

Updates the customer with the given `id`. A new set of `payment_details` may be specified.

### Example

```typescript
const result = await api.updateCustomer({
  id: 'YOUR_ID',
  updateCustomerRequest: {
    // See UpdateCustomerRequest for all available fields
  },
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** |  | [default to null] |
| **updateCustomerRequest** | [**UpdateCustomerRequest**](../Models/UpdateCustomerRequest.md) |  | |

### Return type

[**Customer**](../Models/Customer.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

