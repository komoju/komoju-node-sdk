# CreateSessionRequestWithCustomerPaymentMode

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **mode** | **String** | In &#x60;customer_payment&#x60; mode, a payment will be created and:  * If &#x60;customer_id&#x60; is omitted, a new customer will be created. * If &#x60;customer_id&#x60; is given, updated payment information will be saved to that customer. | [default to null] |
| **return\_url** | **String** | Specify the URL where user will be redirected to after they have completed or aborted the session. A &#x60;session_id&#x60; will be appended to this URL as a query parameter. | [optional] [default to null] |
| **amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **email** | **String** | Customer&#39;s email address. | [optional] [default to null] |
| **expires\_in\_seconds** | **Integer** | Time in seconds until the session expires after being created.  The default value and upper limit are 86,400 seconds (24 hours). | [optional] [default to null] |
| **external\_customer\_id** | **String** | An unique identifier of your customer. If your system has the concept of user accounts, then the ID of the current logged in user would be appropriate. | [optional] [default to null] |
| **payment\_types** | [**List**](PaymentType.md) | Specify which payment types are available for this session.  By default, all activated payment methods will be available for the session if this value is omitted. | [optional] [default to null] |
| **default\_locale** | [**Locale**](Locale.md) |  | [optional] [default to null] |
| **line\_items** | [**List**](LineItem.md) | Specify the line items which will be displayed on the session page. | [optional] [default to null] |
| **metadata** | [**Object**](.md) | Store any additional data you want to associate with the session. The object&#39;s keys and values must be strings. Keys have a maximum length of 30 characters. Values have a maximum length of 2000 characters. | [optional] [default to null] |
| **payment\_data** | [**PaymentDataRequest**](PaymentDataRequest.md) |  | [optional] [default to null] |
| **customer\_id** | **String** | If provided, updated payment details will be saved on the customer. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

