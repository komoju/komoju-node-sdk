# CreatePaymentRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **amount** | **Integer** | The payment amount before tax, greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **capture** | **Boolean** | If &#x60;false&#x60;, the payment will be authorized on success, and you must manually capture it later to secure funds.  The payment will be captured immediately if omitted. | [optional] [default to null] |
| **description** | **String** | A description from your application for this payment. | [optional] [default to null] |
| **tax** | [**CreatePaymentRequestWithPaymentDetails_tax**](CreatePaymentRequestWithPaymentDetails_tax.md) |  | [optional] [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **external\_order\_num** | **String** | A unique ID from your application used to track this payment. | [optional] [default to null] |
| **return\_url** | **String** | For offsite payment methods, specify the URL where user will be redirected to after they have completed the payment. | [optional] [default to null] |
| **cancel\_url** | **String** | For offsite payment methods, specify the URL where user will be redirected to if they cancel the payment. | [optional] [default to null] |
| **locale** | [**Locale**](Locale.md) |  | [optional] [default to null] |
| **metadata** | [**Object**](.md) | Specify a key-value map which will be stored on the payment. You can use this field to store metadata related to this payment. Keys and values must be strings. Keys have a maximum length of 30 characters. Values have a maximum length of 2000 characters. | [optional] [default to null] |
| **mcc** | **String** | On supported merchant and supported payment methods, specify a custom Merchant Category Code (MCC) for this payment.  See [Dynamic Statement Descriptors &amp; MCCs](https://doc.komoju.com/docs/payments-with-dynamic-statement-descriptors) for more information. | [optional] [default to null] |
| **statement\_descriptor** | [**StatementDescriptor**](StatementDescriptor.md) |  | [optional] [default to null] |
| **fraud\_details** | [**FraudDetails**](FraudDetails.md) |  | [optional] [default to null] |
| **platform\_details** | [**PlatformDetails**](PlatformDetails.md) |  | [optional] [default to null] |
| **payment\_details** | [**PaymentDetailsAll**](PaymentDetailsAll.md) |  | [default to null] |
| **customer** | **String** | For a subscription payment, specify customer&#39;s identifier for this payment.  This identifier can be obtained from [Customer: Create](https://doc.komoju.com/reference/createcustomer) endpoint. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

