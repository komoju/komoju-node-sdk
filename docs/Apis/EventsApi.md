# EventsApi

All URIs are relative to *https://komoju.com/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listEvents**](EventsApi.md#listEvents) | **GET** /events | Event: List |
| [**showEvent**](EventsApi.md#showEvent) | **GET** /events/{id} | Event Show |


## Setup

```typescript
import { Configuration, EventsApi } from 'komoju-typescript-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const api = new EventsApi(config);
```

## listEvents

> EventList listEvents(startTime, endTime, perPage, page)

Event: List

Lists out past webhook events from most-recent to least-recent.

### Example

```typescript
const result = await api.listEvents({
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

[**EventList**](../Models/EventList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

## showEvent

> Event showEvent(id)

Event Show

View an event given an `id`. Event `id`s can be saved from a webhook or found by querying all events.

### Example

```typescript
const result = await api.showEvent({
  id: 'YOUR_ID',
});
console.log(result.data);
```

### Parameters

| Name | Type | Description | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String** | A unique identifier for an event. | [default to null] |

### Return type

[**Event**](../Models/Event.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

