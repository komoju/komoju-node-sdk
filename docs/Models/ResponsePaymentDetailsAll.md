# ResponsePaymentDetailsAll

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **type** | **String** | Payment method type. | [default to null] |
| **brand** | **String** | Card brand (e.g. \&quot;visa\&quot;, \&quot;mastercard\&quot;). | [default to null] |
| **last\_four\_digits** | **String** | Last four digits of the card used. | [default to null] |
| **month** | **Integer** | Credit card expiration month. | [default to null] |
| **year** | **Integer** | Credit card expiration year.  If this value is less than 100, it will be treated as two digits year in the current century. E.g. If current year is &#x60;2024&#x60;, &#x60;99&#x60; means &#x60;2099&#x60;. | [default to null] |
| **email** | **String** | Customer&#39;s email address. Will be used for fraud prevention and payment receipt. | [default to null] |
| **verification\_value** | **String** |  | [optional] [default to null] |
| **name** | **String** | Full name of the customer.  This attribute takes precedence over &#x60;given_name&#x60; and &#x60;family_name&#x60;. | [optional] [default to null] |
| **given\_name** | **String** | Given name of the customer. | [optional] [default to null] |
| **family\_name** | **String** | Family name of the customer. | [optional] [default to null] |
| **expiry\_days** | **Integer** |  | [optional] [default to null] |
| **intent** | **String** |  | [optional] [default to null] |
| **initiator** | **String** |  | [optional] [default to null] |
| **usage** | **String** |  | [optional] [default to null] |
| **scheme\_reference** | **String** |  | [optional] [default to null] |
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
| **remote\_payment\_id** | **String** | Remote payment identifier returned by the Brazilian payment gateway. | [default to null] |
| **field55** | **String** |  | [optional] [default to null] |
| **cardnet\_status** | **String** | Status code returned by the Cardnet network. | [optional] [default to null] |
| **approval\_number** | **String** | Approval number returned by the card network. | [optional] [default to null] |
| **transaction\_id** | **String** | Transaction identifier returned by UnionPay. | [optional] [default to null] |
| **redirect\_url** | **String** | URL to redirect the customer to for completing the WeChat Pay payment. | [optional] [default to null] |
| **pay\_info\_no** | **String** | Payment information number for this au transaction. | [optional] [default to null] |
| **transaction\_key** | **String** | Transaction key returned by Sofort. | [optional] [default to null] |
| **order\_id** | **String** | Order identifier for this bank transfer. | [optional] [default to null] |
| **bank\_name** | **String** | Name of the bank to transfer funds to. | [optional] [default to null] |
| **account\_branch\_name** | **String** | Name of the bank branch. | [optional] [default to null] |
| **account\_number** | **String** | Bank account number to transfer funds to. | [optional] [default to null] |
| **account\_type** | **String** | Type of bank account. | [optional] [default to null] |
| **account\_name** | **String** | Name of the bank account holder. | [optional] [default to null] |
| **instructions\_url** | **String** | URL with payment instructions for the customer. | [optional] [default to null] |
| **payment\_deadline** | **Date** | Deadline by which the bank transfer must be completed. | [optional] [default to null] |
| **culture\_id** | **String** | Culture Land ID used for this voucher payment. | [default to null] |
| **bardcode** | **String** | Barcode number for the CVS payment slip. | [optional] [default to null] |
| **provider\_order\_number** | **String** | Order number provided by carrier. | [optional] [default to null] |
| **user\_no** | **String** | Dospara user number used for this payment. | [default to null] |
| **offsite\_fake\_new\_path** | **String** | When using test mode. | [optional] [default to null] |
| **offsite\_url** | **String** | URL for the customer to complete the EPOS payment offsite. | [optional] [default to null] |
| **merchant\_id** | **String** | Merchant identifier used in the EPOS payment request. | [optional] [default to null] |
| **shop\_id** | **String** | Shop identifier used in the EPOS payment request. | [optional] [default to null] |
| **deal\_id** | **String** | Deal identifier for this EPOS transaction. | [optional] [default to null] |
| **token** | **String** | Authentication token for the EPOS payment. | [optional] [default to null] |
| **prd\_list** | **String** | Product list data for the EPOS payment. | [optional] [default to null] |
| **amount** | **Integer** | Payment amount in the lowest denomination of the currency. | [optional] [default to null] |
| **customer\_id** | **String** | Customer identifier for the Pay-easy payment. | [optional] [default to null] |
| **return\_url** | **String** | URL to redirect the customer to after completing the EPOS payment. | [optional] [default to null] |
| **happy\_money\_id** | **String** | Happy Money ID used for this payment. | [default to null] |
| **transacion\_key** | **String** | Transaction key returned by iDEAL. | [optional] [default to null] |
| **store** | **String** |  | [default to null] |
| **confirmation\_code** | **String** | Confirmation code for the konbini payment slip. | [optional] [default to null] |
| **receipt** | **String** | Receipt number for the konbini payment. | [optional] [default to null] |
| **provider** | **String** | Mobile carrier or payment provider for this payment. | [default to null] |
| **callback\_url** | **String** | Callback URL used in the Naver Pay payment flow. | [optional] [default to null] |
| **mode** | **String** | Environment mode for the Naver Pay integration. | [optional] [default to null] |
| **redirect** | **Boolean** | Whether the payment uses a redirect flow. | [optional] [default to null] |
| **client\_id** | **String** | Naver Pay client ID for this merchant. | [optional] [default to null] |
| **digital\_content\_only** | **Boolean** | Whether this payment is for digital content only. | [optional] [default to null] |
| **short\_amount** | **Integer** | Amount the payment is short by if insufficient funds were provided. | [optional] [default to null] |
| **prepaid\_cards** | [**List**](PrepaidCards.md) | List of prepaid cards used in this transaction. | [optional] [default to null] |
| **order\_sheet\_url** | **String** | URL to the PAYCO order sheet for the customer. | [optional] [default to null] |
| **bank\_id** | **String** | Bank identifier for the Pay-easy payment. | [optional] [default to null] |
| **confirmation\_id** | **String** | Confirmation ID for the Pay-easy payment. | [optional] [default to null] |
| **payment\_url** | **String** | URL where the customer can complete the Pay-easy payment online. | [optional] [default to null] |
| **cvs\_code** | **String** | CVS code for convenience store payment. | [optional] [default to null] |
| **external\_payment\_id** | **String** | Payment identifier returned by PayPay. | [optional] [default to null] |
| **transaction\_code** | **String** | PIX transaction code. | [optional] [default to null] |
| **qr\_code\_url** | **String** | URL to the QR code image for the WeChat Pay payment. | [optional] [default to null] |
| **pix\_payment\_code** | **String** | PIX payment code that the customer can use to complete the payment. | [optional] [default to null] |
| **charge\_key** | **String** | Charge key returned by Rakuten Pay. | [optional] [default to null] |
| **toss\_pay\_token** | **String** | Token for the Toss Pay payment flow. | [optional] [default to null] |
| **qr\_code** | **String** | QR code data for the Toss payment. | [optional] [default to null] |
| **mweb\_url** | **String** | Mobile web URL for the WeChat Pay payment flow. | [optional] [default to null] |
| **trade\_type** | **String** | WeChat Pay trade type: NATIVE for QR code, MWEB for mobile web. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

