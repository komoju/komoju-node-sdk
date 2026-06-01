# FraudDetails

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **customer\_ip** | **String** | IPv4 or IPv6-formatted IP address of the customer at the time of payment. | [default to null] |
| **customer\_email** | **String** | Customer&#39;s email address.  This field can be omitted if &#x60;email&#x60; is provided in &#x60;email&#x60; field inside &#x60;payment_details&#x60; of create payment request, or in the create payment session request. Otherwise, this field is required. | [default to null] |
| **customer\_id** | **String** | An unique identifier of your customer. If your system has the concept of user accounts, then the ID of the current logged in user would be appropriate. | [optional] [default to null] |
| **browser\_language** | **String** | Customer&#39;s current language setting. | [optional] [default to null] |
| **browser\_user\_agent** | **String** | Browser&#39;s [User-Agent](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent) string. | [optional] [default to null] |
| **browser\_session\_id** | **String** | A unique identifier for the current browser session. We expect this to behave similarly to the lifetime of [window.sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage) in a web browsing context. | [optional] [default to null] |
| **phone** | **String** | Customer&#39;s phone number. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

