# LiveApplicationRequest

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **locale** | [**Locale**](Locale.md) |  | [optional] [default to null] |
| **service\_agreement.agreed\_to\_tos** | **Boolean** | Whether the merchant has agreed to KOMOJU&#39;s terms of service. | [optional] [default to null] |
| **company\_information.company\_name** | **String** | Registered legal name of the company. | [optional] [default to null] |
| **company\_information.company\_phone** | **String** | Company contact phone number. | [optional] [default to null] |
| **company\_information.company\_country** | [**CountryCode**](CountryCode.md) |  | [optional] [default to null] |
| **company\_information.corporation\_type** | **String** | Whether the business is a sole proprietorship or corporation. | [optional] [default to null] |
| **company\_information.company\_postal\_code** | **String** | Postal code of the company&#39;s registered address. | [optional] [default to null] |
| **company\_information.company\_prefecture\_state** | **String** | Prefecture or state of the company&#39;s registered address. | [optional] [default to null] |
| **company\_information.company\_prefecture\_state\_kana** | **String** | Prefecture or state in katakana. | [optional] [default to null] |
| **company\_information.company\_city** | **String** | City of the company&#39;s registered address. | [optional] [default to null] |
| **company\_information.company\_city\_kana** | **String** | City name in katakana. | [optional] [default to null] |
| **company\_information.company\_address** | **String** | Street address of the company. | [optional] [default to null] |
| **company\_information.industry\_description** | **String** | Description of the industry the company operates in. | [optional] [default to null] |
| **company\_information.business\_description** | **String** | Description of the company&#39;s business activities and products/services sold. | [optional] [default to null] |
| **company\_information.employee\_number** | **String** | Number of employees at the company. | [optional] [default to null] |
| **company\_information.establishment\_date** | **String** | Date the company was established (YYYY-MM-DD format). | [optional] [default to null] |
| **company\_information.office\_name** | **String** | Name of the specific office or branch. | [optional] [default to null] |
| **company\_information.contact\_email** | **String** | Primary contact email address for the company. | [optional] [default to null] |
| **company\_information.contact\_phone** | **String** | Primary contact phone number for the company. | [optional] [default to null] |
| **company\_information.incorporation\_certificates** | **List** | File IDs of uploaded incorporation certificate documents. | [optional] [default to null] |
| **company\_information.registration\_number** | **String** | Company registration number. | [optional] [default to null] |
| **company\_information.share\_capital\_amount** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [optional] [default to null] |
| **company\_information.share\_capital\_currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **company\_information.sole\_proprietor\_proofs** | **List** | File IDs of uploaded sole proprietorship proof documents. | [optional] [default to null] |
| **company\_information.company\_name\_kana** | **String** | Company name in katakana. | [optional] [default to null] |
| **company\_information.company\_name\_alphabet** | **String** | Company name in alphanumeric (Roman) characters. | [optional] [default to null] |
| **company\_information.company\_url** | **String** | URL of the company&#39;s website. | [optional] [default to null] |
| **company\_information.company\_address\_kana** | **String** | Street address in katakana. | [optional] [default to null] |
| **company\_information.company\_address\_building\_name** | **String** | Building name portion of the company address. | [optional] [default to null] |
| **company\_information.company\_address\_building\_name\_kana** | **String** | Building name in katakana. | [optional] [default to null] |
| **representative\_director\_information.first\_name** | **String** | Representative director&#39;s first name. | [optional] [default to null] |
| **representative\_director\_information.first\_name\_kana** | **String** | Representative director&#39;s first name in katakana. | [optional] [default to null] |
| **representative\_director\_information.last\_name** | **String** | Representative director&#39;s last name. | [optional] [default to null] |
| **representative\_director\_information.last\_name\_kana** | **String** | Representative director&#39;s last name in katakana. | [optional] [default to null] |
| **representative\_director\_information.date\_of\_birth** | **String** | Representative director&#39;s date of birth (YYYY-MM-DD format). | [optional] [default to null] |
| **representative\_director\_information.gender** | **String** | Representative director&#39;s gender. | [optional] [default to null] |
| **representative\_director\_information.country** | [**CountryCode**](CountryCode.md) |  | [optional] [default to null] |
| **representative\_director\_information.postal\_code** | **String** | Postal code of the representative director&#39;s address. | [optional] [default to null] |
| **representative\_director\_information.prefecture\_state** | **String** | Prefecture or state of the representative director&#39;s address. | [optional] [default to null] |
| **representative\_director\_information.prefecture\_state\_kana** | **String** | Prefecture or state in katakana. | [optional] [default to null] |
| **representative\_director\_information.city** | **String** | City of the representative director&#39;s address. | [optional] [default to null] |
| **representative\_director\_information.city\_kana** | **String** | City name in katakana. | [optional] [default to null] |
| **representative\_director\_information.address** | **String** | Street address of the representative director. | [optional] [default to null] |
| **representative\_director\_information.address\_kana** | **String** | Street address in katakana. | [optional] [default to null] |
| **representative\_director\_information.address\_building\_name** | **String** | Building name portion of the representative director&#39;s address. | [optional] [default to null] |
| **representative\_director\_information.address\_building\_name\_kana** | **String** | Building name in katakana. | [optional] [default to null] |
| **representative\_director\_information.phone** | **String** | Representative director&#39;s phone number. | [optional] [default to null] |
| **applicant\_information.first\_name** | **String** | Applicant&#39;s first name. | [optional] [default to null] |
| **applicant\_information.first\_name\_kana** | **String** | Applicant&#39;s first name in katakana. | [optional] [default to null] |
| **applicant\_information.last\_name** | **String** | Applicant&#39;s last name. | [optional] [default to null] |
| **applicant\_information.last\_name\_kana** | **String** | Applicant&#39;s last name in katakana. | [optional] [default to null] |
| **applicant\_information.country** | [**CountryCode**](CountryCode.md) |  | [optional] [default to null] |
| **applicant\_information.gender** | **String** | Applicant&#39;s gender. | [optional] [default to null] |
| **applicant\_information.date\_of\_birth** | **String** | Applicant&#39;s date of birth (YYYY-MM-DD format). | [optional] [default to null] |
| **applicant\_information.identity\_document\_type** | **String** | Type of identity document submitted for verification. | [optional] [default to null] |
| **applicant\_information.identity\_front** | **String** | File ID of the front side of the uploaded identity document. | [optional] [default to null] |
| **applicant\_information.identity\_back** | **String** | File ID of the back side of the uploaded identity document. | [optional] [default to null] |
| **site\_information.site\_name** | **String** | Name of the merchant&#39;s website or online store. | [optional] [default to null] |
| **site\_information.site\_name\_kana** | **String** | Site name in katakana. | [optional] [default to null] |
| **site\_information.site\_name\_alphabet** | **String** | Site name in alphanumeric (Roman) characters. | [optional] [default to null] |
| **site\_information.site\_url** | **String** | URL of the merchant&#39;s online store. | [optional] [default to null] |
| **site\_information.establishment\_date** | **String** | Date the online store was established (YYYY-MM-DD format). | [optional] [default to null] |
| **site\_information.store\_country** | [**CountryCode**](CountryCode.md) |  | [optional] [default to null] |
| **site\_information.store\_postal\_code** | **String** | Postal code of the store&#39;s physical location. | [optional] [default to null] |
| **site\_information.store\_prefecture\_state** | **String** | Prefecture or state of the store&#39;s physical location. | [optional] [default to null] |
| **site\_information.store\_prefecture\_state\_kana** | **String** | Prefecture or state in katakana. | [optional] [default to null] |
| **site\_information.store\_city** | **String** | City of the store&#39;s physical location. | [optional] [default to null] |
| **site\_information.store\_city\_kana** | **String** | City name in katakana. | [optional] [default to null] |
| **site\_information.store\_address** | **String** | Street address of the store&#39;s physical location. | [optional] [default to null] |
| **site\_information.store\_address\_kana** | **String** | Store street address in katakana. | [optional] [default to null] |
| **site\_information.store\_building\_name** | **String** | Building name for the store&#39;s address. | [optional] [default to null] |
| **site\_information.store\_building\_name\_kana** | **String** | Building name in katakana. | [optional] [default to null] |
| **site\_information.site\_product\_description** | **String** | Description of the products or services sold on the site. | [optional] [default to null] |
| **site\_information.site\_annual\_sales** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [optional] [default to null] |
| **site\_information.site\_annual\_sales\_currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **site\_information.site\_average\_transactional\_value** | **String** | Average transaction value as a formatted string. | [optional] [default to null] |
| **site\_information.site\_average\_transactional\_currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **site\_information.site\_minimum\_product\_pricing\_cents** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [optional] [default to null] |
| **site\_information.site\_minimum\_product\_pricing\_currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **site\_information.site\_maximum\_product\_pricing\_cents** | **Integer** | Amount greater than or equal to 0, in the lowest denomination of the currency (e.g. cents for USD). | [optional] [default to null] |
| **site\_information.site\_maximum\_product\_pricing\_currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **site\_information.sctl\_url** | **String** | URL of the merchant&#39;s Specified Commercial Transaction Law disclosure page. | [optional] [default to null] |
| **site\_information.sales\_permit\_required** | **Boolean** | Whether a sales permit is required for the merchant&#39;s business type. | [optional] [default to null] |
| **site\_information.aup\_accepted** | **Boolean** | Whether the merchant has accepted the Acceptable Use Policy. | [optional] [default to null] |
| **site\_information.industry\_type** | [**IndustryType**](IndustryType.md) |  | [optional] [default to null] |
| **site\_information.sales\_permits** | **List** | File IDs of uploaded sales permit documents. | [optional] [default to null] |
| **bank\_account\_information.zengin\_bank\_name** | **String** | Name of the merchant&#39;s bank (Zengin network). | [optional] [default to null] |
| **bank\_account\_information.zengin\_bank\_code** | **String** | 4-digit bank code in the Zengin network. | [optional] [default to null] |
| **bank\_account\_information.zengin\_branch\_name** | **String** | Name of the bank branch. | [optional] [default to null] |
| **bank\_account\_information.zengin\_branch\_code** | **String** | 3-digit branch code. | [optional] [default to null] |
| **bank\_account\_information.zengin\_account\_type** | **String** | Type of bank account (ordinary or checking). | [optional] [default to null] |
| **bank\_account\_information.zengin\_account\_number** | **String** | Bank account number. | [optional] [default to null] |
| **bank\_account\_information.zengin\_account\_holder\_kana** | **String** | Account holder name in katakana as registered with the bank. | [optional] [default to null] |
| **bank\_account\_information.transfer\_type** | **String** | Type of bank transfer supported (currently only \&quot;domestic\&quot;). | [optional] [default to null] |
| **bank\_account\_information.currency** | [**Currency**](Currency.md) |  | [optional] [default to null] |
| **bank\_account\_information.default\_frequency** | [**SettlementFrequency**](SettlementFrequency.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

