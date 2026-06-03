# UpdatePaymentMethodRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **locale** | [**Locale**](Locale.md) |  | [optional] [default to null] |
| **shared\_payment\_method\_data.open\_time** | **String** | Business opening time for this merchant&#39;s store. | [optional] [default to null] |
| **shared\_payment\_method\_data.close\_time** | **String** | Business closing time for this merchant&#39;s store. | [optional] [default to null] |
| **shared\_payment\_method\_data.privacy\_policy\_url** | **String** | URL to the merchant&#39;s privacy policy page. | [optional] [default to null] |
| **shared\_payment\_method\_data.terms\_of\_service\_url** | **String** | URL to the merchant&#39;s terms of service page. | [optional] [default to null] |
| **shared\_payment\_method\_data.pci\_compliance\_proofs** | **List** | File IDs of uploaded PCI compliance proof documents. | [optional] [default to null] |
| **shared\_payment\_method\_data.shareholder\_registers** | **List** | File IDs of uploaded shareholder register documents. | [optional] [default to null] |
| **shared\_payment\_method\_data.has\_processed\_cc\_before** | **Boolean** | Whether the merchant has previously processed credit card payments. | [optional] [default to null] |
| **shared\_payment\_method\_data.processes\_card\_info** | **Boolean** | Whether the merchant directly handles or stores card information. | [optional] [default to null] |
| **shared\_payment\_method\_data.conducts\_door\_to\_door\_sales** | **Boolean** | Whether the merchant conducts door-to-door sales. | [optional] [default to null] |
| **shared\_payment\_method\_data.conducts\_telemarketing** | **Boolean** | Whether the merchant conducts telemarketing activities. | [optional] [default to null] |
| **shared\_payment\_method\_data.conducts\_mlm\_scheme** | **Boolean** | Whether the merchant operates a multi-level marketing scheme. | [optional] [default to null] |
| **shared\_payment\_method\_data.conducts\_business\_opportunity\_scheme** | **Boolean** | Whether the merchant offers business opportunity schemes. | [optional] [default to null] |
| **shared\_payment\_method\_data.provides\_specified\_continuous\_services** | **Boolean** | Whether the merchant provides services subject to the Specified Commercial Transaction Act. | [optional] [default to null] |
| **shared\_payment\_method\_data.violated\_consumer\_contract\_act** | **Boolean** | Whether the merchant has violated the Consumer Contract Act. | [optional] [default to null] |
| **shared\_payment\_method\_data.violated\_commercial\_transaction\_act** | **Boolean** | Whether the merchant has violated the Commercial Transaction Act. | [optional] [default to null] |
| **linepay.accepted\_line\_tos** | **Boolean** | Whether the merchant has accepted LINE Pay&#39;s terms of service. | [optional] [default to null] |
| **linepay.fields** | **String** | Serialized form fields for the LINE Pay application. | [optional] [default to null] |
| **paypay.accepted\_paypay\_tos** | **Boolean** | Whether the merchant has accepted PayPay&#39;s terms of service. | [optional] [default to null] |
| **paypay.fields** | **String** | Serialized form fields for the PayPay application. | [optional] [default to null] |
| **merpay.accepted\_merpay\_tos** | **Boolean** | Whether the merchant has accepted Merpay&#39;s terms of service. | [optional] [default to null] |
| **merpay.fields** | **String** | Serialized form fields for the Merpay application. | [optional] [default to null] |
| **convenience\_store.expected\_number\_of\_payments** | **Integer** | Estimated monthly number of convenience store payments. | [optional] [default to null] |
| **convenience\_store.fields** | **String** | Serialized form fields for the convenience store application. | [optional] [default to null] |
| **seven\_eleven.site\_is\_public** | **Boolean** | Whether the merchant&#39;s website is publicly accessible. | [optional] [default to null] |
| **seven\_eleven.no\_direct\_delivery\_from\_producer** | **Boolean** | Confirmation that products are not delivered directly from producers. | [optional] [default to null] |
| **seven\_eleven.no\_ticket\_sales** | **Boolean** | Confirmation that the merchant does not sell tickets. | [optional] [default to null] |
| **seven\_eleven.correct\_flow\_for\_order\_items** | **Boolean** | Confirmation that the order flow matches Seven-Eleven&#39;s requirements. | [optional] [default to null] |
| **seven\_eleven.delivery\_within\_two\_months** | **Boolean** | Confirmation that all ordered items will be delivered within two months. | [optional] [default to null] |
| **seven\_eleven.all\_items\_are\_cheaper\_than\_konbini\_limit** | **Boolean** | Confirmation that all items are priced below the konbini payment limit. | [optional] [default to null] |
| **seven\_eleven.display\_sales\_permit\_number** | **Boolean** | Confirmation that any required sales permit numbers are displayed. | [optional] [default to null] |
| **seven\_eleven.order\_fee\_is\_displayed** | **Boolean** | Confirmation that the order fee is clearly displayed to customers. | [optional] [default to null] |
| **seven\_eleven.no\_international\_transaction** | **Boolean** | Confirmation that transactions are domestic only. | [optional] [default to null] |
| **seven\_eleven.provided\_info\_matches\_sctl** | **Boolean** | Confirmation that site info matches the Specified Commercial Transaction Law disclosure page. | [optional] [default to null] |
| **seven\_eleven.sctl\_page\_has\_phone\_number** | **Boolean** | Confirmation that the SCTL page includes a phone number. | [optional] [default to null] |
| **seven\_eleven.product\_pages\_are\_public** | **Boolean** | Confirmation that product detail pages are publicly viewable. | [optional] [default to null] |
| **seven\_eleven.have\_sold\_as\_regular\_price** | **Boolean** | Confirmation that items have been sold at regular (non-discounted) price before. | [optional] [default to null] |
| **seven\_eleven.note** | **String** | Free-text notes for the Seven-Eleven application. | [optional] [default to null] |
| **seven\_eleven.fields** | **String** | Serialized form fields for the Seven-Eleven application. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.access\_restrictions** | **Boolean** | Confirmation that the site has appropriate access restrictions in place. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.mfa\_implementation** | **Boolean** | Confirmation that multi-factor authentication is implemented. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.account\_lock** | **Boolean** | Confirmation that account lockout policies are in place. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.public\_directories** | **Boolean** | Confirmation that public directory listing is disabled. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.file\_extension\_restrictions** | **Boolean** | Confirmation that file extension restrictions are enforced. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.vulnerability\_assessments** | **Boolean** | Confirmation that regular vulnerability assessments are conducted. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.sql\_injection\_and\_xss** | **Boolean** | Confirmation that the site is protected against SQL injection and XSS attacks. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.source\_code\_review** | **Boolean** | Confirmation that source code security review is performed. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.anti\_virus\_software** | **Boolean** | Confirmation that anti-virus software is installed and maintained. | [optional] [default to null] |
| **visa\_mastercard\_credit\_card.fields** | **String** | Serialized form fields for the Visa/Mastercard credit card application. | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.access\_restrictions** | **Boolean** | Confirmation that the site has appropriate access restrictions in place (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.mfa\_implementation** | **Boolean** | Confirmation that multi-factor authentication is implemented (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.account\_lock** | **Boolean** | Confirmation that account lockout policies are in place (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.public\_directories** | **Boolean** | Confirmation that public directory listing is disabled (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.file\_extension\_restrictions** | **Boolean** | Confirmation that file extension restrictions are enforced (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.vulnerability\_assessments** | **Boolean** | Confirmation that regular vulnerability assessments are conducted (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.sql\_injection\_and\_xss** | **Boolean** | Confirmation that the site is protected against SQL injection and XSS attacks (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.source\_code\_review** | **Boolean** | Confirmation that source code security review is performed (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.anti\_virus\_software** | **Boolean** | Confirmation that anti-virus software is installed and maintained (JCB/Amex/Diners). | [optional] [default to null] |
| **jcb\_amex\_diners\_credit\_card.fields** | **String** | Serialized form fields for the JCB/Amex/Diners credit card application. | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

