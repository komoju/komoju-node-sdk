# SettlementShow

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **resource** | **String** | Resource type name, always \&quot;settlement\&quot;. | [default to null] |
| **reference** | **String** | Human-readable reference code for this settlement. | [default to null] |
| **status** | [**Status**](Status.md) |  | [default to null] |
| **merchant\_name** | **String** | Name of the merchant associated with this settlement. | [default to null] |
| **company\_name** | **String** | Legal company name of the merchant, or null if not set. | [default to null] |
| **cycle** | **String** | Settlement cycle identifier (e.g. the week or month period covered). | [default to null] |
| **transaction\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **currency** | [**Currency**](Currency.md) |  | [default to null] |
| **fee\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **fee\_tax\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **settlement\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **fx\_currency** | [**Currency**](Currency.md) |  | [default to null] |
| **fx\_conversion\_rate** | **String** | Exchange rate applied for FX conversion. | [default to null] |
| **fx\_conversion\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **bank\_transfer\_fee\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **remittance\_amount\_cents** | **Integer** | Amount in the lowest denomination of the currency (e.g. cents for USD). | [default to null] |
| **cutoff\_time** | **Date** | Cutoff timestamp for transactions included in this settlement. | [default to null] |
| **created\_at** | **Date** | Timestamp when this settlement record was created. | [default to null] |
| **download** | [**Settlement_download**](Settlement_download.md) |  | [default to null] |
| **payments** | [**SharedDetails_payments**](SharedDetails_payments.md) |  | [default to null] |
| **refunds** | [**SharedDetails_refunds**](SharedDetails_refunds.md) |  | [default to null] |
| **platform\_model** | [**SharedDetails_platform_model**](SharedDetails_platform_model.md) |  | [optional] [default to null] |
| **corrections** | [**SharedDetails_corrections**](SharedDetails_corrections.md) |  | [default to null] |
| **komoju\_card\_charges** | [**SharedDetails_corrections**](SharedDetails_corrections.md) |  | [default to null] |
| **disbursements** | [**SharedDetails_disbursements**](SharedDetails_disbursements.md) |  | [default to null] |
| **misc** | [**SharedDetails_misc**](SharedDetails_misc.md) |  | [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

