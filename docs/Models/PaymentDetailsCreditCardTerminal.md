# PaymentDetailsCreditCardTerminal

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **number** | **String** | Credit card number. | [default to null] |
| **month** | **Integer** | Credit card expiration month. | [optional] [default to null] |
| **year** | **Integer** | Credit card expiration year.  If this value is less than 100, it will be treated as two digits year in the current century. E.g. If current year is &#x60;2024&#x60;, &#x60;99&#x60; means &#x60;2099&#x60;. | [optional] [default to null] |
| **sequence\_number** | **String** | Specify the sequence number from the credit card terminal | [optional] [default to null] |
| **field55** | **String** | Specify the EMV data produced by the terminal. | [optional] [default to null] |
| **posDataCode** | **String** | Specify the POS data code produced by the terminal. | [optional] [default to null] |
| **track2** | **String** | Specify the data read from track 2 of the payment card. | [optional] [default to null] |
| **flowType** | **String** | Specify whether this transaction is a EMV or magnetic stripe transaction.  - Use value \&quot;1\&quot; for EMV transaction. - Use value \&quot;2\&quot; for magnetic stripe transaction. | [optional] [default to null] |
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

