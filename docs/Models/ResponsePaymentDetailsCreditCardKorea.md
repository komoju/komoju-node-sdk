# ResponsePaymentDetailsCreditCardKorea

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **brand** | **String** | Card brand (e.g. \&quot;visa\&quot;, \&quot;mastercard\&quot;, \&quot;jcb\&quot;). | [default to null] |
| **last\_four\_digits** | **String** | Last four digits of the card number. | [default to null] |
| **month** | **Integer** | Credit card expiration month. | [default to null] |
| **year** | **Integer** | Credit card expiration year.  If this value is less than 100, it will be treated as two digits year in the current century. E.g. If current year is &#x60;2024&#x60;, &#x60;99&#x60; means &#x60;2099&#x60;. | [default to null] |
| **verification\_value** | **String** |  | [optional] [default to null] |
| **shipping\_address\_name** | **String** | Shipping address name. This is the recipient&#39;s name. | [optional] [default to null] |
| **shipping\_address\_line1** | **String** | Shipping address line 1. | [optional] [default to null] |
| **shipping\_address\_line2** | **String** | Shipping address line 2. | [optional] [default to null] |
| **shipping\_address\_city** | **String** | Shipping address city. | [optional] [default to null] |
| **shipping\_address\_state** | **String** | Shipping address state. | [optional] [default to null] |
| **shipping\_address\_zip** | **String** | Shipping address ZIP code. | [optional] [default to null] |
| **shipping\_address\_country** | **String** | Shipping address country. | [optional] [default to null] |
| **billing\_address\_name** | **String** | Billing address name. This is the paying customer&#39;s name. | [optional] [default to null] |
| **billing\_address\_line1** | **String** | Billing address line 1. | [optional] [default to null] |
| **billing\_address\_line2** | **String** | Billing address line 2. | [optional] [default to null] |
| **billing\_address\_city** | **String** | Billing address city. | [optional] [default to null] |
| **billing\_address\_state** | **String** | Billing address state. | [optional] [default to null] |
| **billing\_address\_zip** | **String** | Billing address ZIP code. | [optional] [default to null] |
| **billing\_address\_country** | **String** | Billing address country. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

