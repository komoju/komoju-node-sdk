# PaymentDetailsAll

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **email** | **String** | Customer&#39;s email address. Will be used for fraud prevention and payment receipt. | [default to null] |
| **number** | **String** | Credit card number. | [default to null] |
| **month** | **Integer** | Credit card expiration month. | [default to null] |
| **year** | **Integer** | Credit card expiration year.  If this value is less than 100, it will be treated as two digits year in the current century. E.g. If current year is &#x60;2024&#x60;, &#x60;99&#x60; means &#x60;2099&#x60;. | [default to null] |
| **verification\_value** | **String** | Credit card verification value (Also known as CVV2 or CVC2). | [default to null] |
| **name** | **String** | Full name of the customer.  This attribute takes precedence over &#x60;given_name&#x60; and &#x60;family_name&#x60;. | [default to null] |
| **given\_name** | **String** | Given name of the customer. | [default to null] |
| **family\_name** | **String** | Family name of the customer. | [default to null] |
| **expiry\_days** | **Integer** | Specify how many days before the payment expires.  If this value is omitted, the default expiry day shown in the merchant dashboard will be used. | [optional] [default to null] |
| **intent** | [**Intent**](Intent.md) |  | [optional] [default to null] |
| **initiator** | **String** | Specify the initiator of this payment.  Specifying this attribute can increase authorization credit card payments authorization rates, especially when using a stored card.  You can set this value to &#x60;customer&#x60; when the payment is being made for one-time goods or service purchase, or &#x60;merchant&#x60; for recurring subscription or installment payments. | [optional] [default to null] |
| **usage** | **String** | Specify whether this payment is the first (&#x60;first&#x60;) or a subsequent payment in a series (&#x60;used&#x60;).  Specifying this attribute can increase authorization credit card payments authorization rates, especially when using a stored card. | [optional] [default to null] |
| **scheme\_reference** | **String** | Specify a scheme reference value, which is used to track the chain of multiple related payments.  This value can be subscription number for a recurring subscription payments, or installment agreement number for installment payments.  Specifying this attribute can increase authorization credit card payments authorization rates, especially when using a stored card. | [optional] [default to null] |
| **installments** | [**Installments**](Installments.md) |  | [optional] [default to null] |
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
| **cpf\_or\_cnpj** | **String** | Specify customer&#39;s CPF or CNPJ. | [default to null] |
| **customer\_ip** | **String** | Specify customer&#39;s IPv4 or IPv6-formatted IP address of the customer. | [default to null] |
| **corporate\_card** | **Boolean** | Specify whether this payment card is a corporate card. | [optional] [default to null] |
| **social\_id** | [**PaymentDetailsCreditCardKorea_social_id**](PaymentDetailsCreditCardKorea_social_id.md) |  | [optional] [default to null] |
| **first\_two\_digits\_of\_pin** | **String** | Specify the first four digit of credit card&#39;s PIN number. | [default to null] |
| **sequence\_number** | **String** | Specify the sequence number from the credit card terminal | [optional] [default to null] |
| **field55** | **String** | Specify the EMV data produced by the terminal. | [optional] [default to null] |
| **posDataCode** | **String** | Specify the POS data code produced by the terminal. | [optional] [default to null] |
| **track2** | **String** | Specify the data read from track 2 of the payment card. | [optional] [default to null] |
| **flowType** | **String** | Specify whether this transaction is a EMV or magnetic stripe transaction.  - Use value \&quot;1\&quot; for EMV transaction. - Use value \&quot;2\&quot; for magnetic stripe transaction. | [optional] [default to null] |
| **scanned\_code** | **String** |  | [optional] [default to null] |
| **phone** | **String** | Customer&#39;s phone number | [default to null] |
| **given\_name\_kana** | **String** | Given name of the customer, written in katakana characters. | [default to null] |
| **family\_name\_kana** | **String** | Family name of the customer, written in katakana characters. | [default to null] |
| **prepaid\_number** | **String** | Prepaid card number. | [default to null] |
| **culture\_id** | **String** | Culture Land ID. | [default to null] |
| **culture\_password** | **String** | Culture Land password. | [default to null] |
| **user\_no** | **String** | Dospara user number. | [default to null] |
| **user\_password** | **String** | Dospara user password. | [default to null] |
| **happy\_money\_id** | **String** | Happy Money ID. | [default to null] |
| **happy\_money\_password** | **String** | Happy Money password. | [default to null] |
| **store** | **String** | Specify the name of convenience store user will make payment from. | [default to null] |
| **brand** | **String** | Specify the carrier. | [default to null] |
| **customer\_age** | **Integer** |  | [optional] [default to null] |
| **customer\_last\_order\_amount** | **Integer** |  | [optional] [default to null] |
| **customer\_last\_order\_at** | **Integer** |  | [optional] [default to null] |
| **customer\_lifetime\_value** | **Integer** |  | [optional] [default to null] |
| **customer\_name** | **String** |  | [default to null] |
| **customer\_order\_count** | **Integer** |  | [optional] [default to null] |
| **external\_customer\_id** | **String** |  | [optional] [default to null] |
| **item\_title** | **String** |  | [optional] [default to null] |
| **customer\_name\_kana** | **String** |  | [optional] [default to null] |
| **capture** | **Boolean** |  | [optional] [default to null] |
| **user\_authorization\_id** | **String** |  | [optional] [default to null] |
| **cpf** | **String** | Customer&#39;s CPF number | [default to null] |
| **birthday** | **String** | Customer&#39;s date of birth in &#x60;YYMMDD&#x60; format. | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

