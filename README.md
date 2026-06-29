## @komoju/komoju-sdk @1.0.0

The KOMOJU Node SDK is a full-featured TypeScript/JavaScript client for the KOMOJU Payments API. It works with any Node.js application or framework.

For a full reference of all available endpoints and models, see the [KOMOJU API Reference](https://doc.komoju.com/reference/getting-started).

### Installation

```
npm install @komoju/komoju-sdk@1.0.0
```

### Getting Started

Get your API keys from the [KOMOJU Merchant Settings](https://komoju.com/merchant/settings) and configure the client.

```typescript
import { Configuration, SessionsApi } from '@komoju/komoju-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');
```

### Example: Hosted Page Payment

The following example walks through a basic hosted page payment flow. For a full guide, see the [Hosted Page Integration Guide](https://doc.komoju.com/docs/hosted-page-integration-guide).

#### 1. Creating a Session

When your customer is ready to pay, create a session and redirect them to the returned `sessionUrl`.

```typescript
const sessionsApi = new SessionsApi(config);

const session = await sessionsApi.createSession({
  createSessionRequest: {
    amount: 1000,
    currency: 'JPY',
    returnUrl: 'https://your-site.com/orders/return',
  },
});

res.redirect(session.data.sessionUrl);
```

#### 2. Handling the Return URL

After the customer pays, KOMOJU redirects them back to your `returnUrl` with a `session_id` query param appended:

```
https://your-site.com/orders/return?session_id=xxxxx
```

Fetch the session to check the outcome:

```typescript
const { session_id } = req.query;

const result = await sessionsApi.showSession({ id: session_id });
const komojuSession = result.data;

if (komojuSession.status === SessionStatus.Completed) {
  // payment.status will be "captured", "authorized", or "pending"
  console.log(`Payment ${komojuSession.payment.status}`);
} else {
  console.log('Payment was cancelled or failed');
}
```

#### 3. Set Up Webhooks (Recommended)

It is possible that the redirect in step 2 fails, possibly due to the user closing their browser, network issues, etc. Or, that the capture will only take place later on, such as with Convenience Store payments. To account for this, we recommend setting up a [Webhook](https://doc.komoju.com/docs/webhooks) to listen for payment events such as `payment.captured`, `payment.authorized`, and `payment.cancelled`. Configure your webhook URL in the [KOMOJU Merchant Dashboard](https://komoju.com/merchant/settings).

##### Verifying Webhook Signatures

To ensure a webhook request genuinely came from KOMOJU, set a **secret token** when creating or updating the webhook. KOMOJU then signs every delivery with a SHA-256 HMAC of the raw request body in the `X-Komoju-Signature` header, which you can recompute and verify.

See [Webhooks → Secret Token](https://doc.komoju.com/docs/webhooks#secret-token) for the full explanation and code examples.

### API Endpoints

All URIs are relative to *https://komoju.com/api/v1*

| Class | Method | HTTP request | Description |
|------------ | ------------- | ------------- | -------------|
| *BarcodesApi* | [**showBarcode**](docs/BarcodesApi.md#showbarcode) | **GET** /barcodes/{payment_id} | Barcode: Show |
| *ChargebacksApi* | [**acceptChargebackRequest**](docs/ChargebacksApi.md#acceptchargebackrequest) | **POST** /chargeback_requests/{id}/accept | Chargeback: Accept |
| *ChargebacksApi* | [**defendChargebackRequest**](docs/ChargebacksApi.md#defendchargebackrequest) | **POST** /chargeback_requests/{id}/defend | Chargeback: Defend |
| *ChargebacksApi* | [**listChargebackRequests**](docs/ChargebacksApi.md#listchargebackrequests) | **GET** /chargeback_requests | Chargeback: List |
| *ChargebacksApi* | [**showChargebackRequest**](docs/ChargebacksApi.md#showchargebackrequest) | **GET** /chargeback_requests/{id} | Chargeback: Show |
| *DisbursementsApi* | [**cancelDisbursement**](docs/DisbursementsApi.md#canceldisbursement) | **POST** /disbursements/{id}/cancel | Disbursement: Cancel |
| *DisbursementsApi* | [**createDisbursement**](docs/DisbursementsApi.md#createdisbursement) | **POST** /disbursements | Disbursement: Create |
| *DisbursementsApi* | [**disbursementReport**](docs/DisbursementsApi.md#disbursementreport) | **GET** /disbursements/report | Disbursement: Report |
| *DisbursementsApi* | [**listDisbursements**](docs/DisbursementsApi.md#listdisbursements) | **GET** /disbursements | Disbursement: List |
| *DisbursementsApi* | [**showDisbursement**](docs/DisbursementsApi.md#showdisbursement) | **GET** /disbursements/{id} | Disbursement: Show |
| *EventsApi* | [**listEvents**](docs/EventsApi.md#listevents) | **GET** /events | Event: List |
| *EventsApi* | [**showEvent**](docs/EventsApi.md#showevent) | **GET** /events/{id} | Event Show |
| *OneClickApi* | [**deleteExternalCustomer**](docs/OneClickApi.md#deleteexternalcustomer) | **DELETE** /external_customers/{id} | External Customer: Destroy |
| *PaymentsApi* | [**cancelPayment**](docs/PaymentsApi.md#cancelpayment) | **POST** /payments/{id}/cancel | Payment: Cancel |
| *PaymentsApi* | [**capturePayment**](docs/PaymentsApi.md#capturepayment) | **POST** /payments/{id}/capture | Payment: Capture |
| *PaymentsApi* | [**createPayment**](docs/PaymentsApi.md#createpayment) | **POST** /payments | Payment: Create |
| *PaymentsApi* | [**createRefundRequest**](docs/PaymentsApi.md#createrefundrequest) | **POST** /payments/{id}/refund_request | Payment: Refund Request |
| *PaymentsApi* | [**finalizePayment**](docs/PaymentsApi.md#finalizepayment) | **POST** /payments/{id}/finalize | Payment: Finalize |
| *PaymentsApi* | [**listPaymentMethods**](docs/PaymentsApi.md#listpaymentmethods) | **GET** /payment_methods | Payment Method: List |
| *PaymentsApi* | [**listPayments**](docs/PaymentsApi.md#listpayments) | **GET** /payments | Payment: List |
| *PaymentsApi* | [**refundPayment**](docs/PaymentsApi.md#refundpayment) | **POST** /payments/{id}/refund | Payment: Refund |
| *PaymentsApi* | [**showPayment**](docs/PaymentsApi.md#showpayment) | **GET** /payments/{id} | Payment: Show |
| *PaymentsApi* | [**updatePayment**](docs/PaymentsApi.md#updatepayment) | **PATCH** /payments/{id} | Payment: Update |
| *PlatformModelApi* | [**balanceTransfer**](docs/PlatformModelApi.md#balancetransfer) | **POST** /balances/{currency}/transfer | Balance: Transfer |
| *PlatformModelApi* | [**createFile**](docs/PlatformModelApi.md#createfile) | **POST** /merchants/{merchant_id}/files | File: Create |
| *PlatformModelApi* | [**createMerchant**](docs/PlatformModelApi.md#createmerchant) | **POST** /merchants | Merchant: Create |
| *PlatformModelApi* | [**createMerchantBalanceTransfer**](docs/PlatformModelApi.md#createmerchantbalancetransfer) | **POST** /merchants/{merchant_id}/balances/{currency}/transfer | Balance: Transfer |
| *PlatformModelApi* | [**editMerchantBalanceSettings**](docs/PlatformModelApi.md#editmerchantbalancesettings) | **PUT** /merchants/{merchant_id}/balances/{currency}/settings | Balances: Edit Settings |
| *PlatformModelApi* | [**listLiveApplicationPaymentMethods**](docs/PlatformModelApi.md#listliveapplicationpaymentmethods) | **GET** /live_application/{merchant_id}/payment_methods | Live Application: Payment Methods |
| *PlatformModelApi* | [**listMerchants**](docs/PlatformModelApi.md#listmerchants) | **GET** /merchants | Merchant: List |
| *PlatformModelApi* | [**listSubmerchantPayments**](docs/PlatformModelApi.md#listsubmerchantpayments) | **GET** /merchants/{merchant_id}/payments | Payment: List for Merchant |
| *PlatformModelApi* | [**listSubmerchantSettlements**](docs/PlatformModelApi.md#listsubmerchantsettlements) | **GET** /merchants/{merchant_id}/settlements | Settlement: List |
| *PlatformModelApi* | [**merchantBalanceTransactions**](docs/PlatformModelApi.md#merchantbalancetransactions) | **GET** /merchants/{merchant_id}/balances/{currency}/transactions | Balance: Transactions |
| *PlatformModelApi* | [**showFile**](docs/PlatformModelApi.md#showfile) | **GET** /merchants/{merchant_id}/files/{id} | File: Show |
| *PlatformModelApi* | [**showLiveApplication**](docs/PlatformModelApi.md#showliveapplication) | **GET** /live_application/{merchant_id} | Live Application: Show |
| *PlatformModelApi* | [**showLiveApplicationPaymentMethod**](docs/PlatformModelApi.md#showliveapplicationpaymentmethod) | **GET** /live_application/{merchant_id}/payment_methods/{payment_method} | Live Application: Show Payment Method |
| *PlatformModelApi* | [**showMerchant**](docs/PlatformModelApi.md#showmerchant) | **GET** /merchants/{id} | Merchant: Show |
| *PlatformModelApi* | [**showMerchantBalance**](docs/PlatformModelApi.md#showmerchantbalance) | **GET** /merchants/{merchant_id}/balances/{currency} | Balance: Show |
| *PlatformModelApi* | [**showMerchantBalanceSettings**](docs/PlatformModelApi.md#showmerchantbalancesettings) | **GET** /merchants/{merchant_id}/balances/{currency}/settings | Balance: Show Settings |
| *PlatformModelApi* | [**showMerchantBalanceTransaction**](docs/PlatformModelApi.md#showmerchantbalancetransaction) | **GET** /merchants/{merchant_id}/balances/{currency}/transactions/{transaction_uuid} | Balance: Transaction |
| *PlatformModelApi* | [**showSubmerchantSettlement**](docs/PlatformModelApi.md#showsubmerchantsettlement) | **GET** /merchants/{merchant_id}/settlements/{id} | Settlement: Show |
| *PlatformModelApi* | [**simulateLiveApplicationPaymentMethodStatus**](docs/PlatformModelApi.md#simulateliveapplicationpaymentmethodstatus) | **PATCH** /live_application/{merchant_id}/payment_methods/{payment_method}/simulate_status | Live Application: Simulate Payment Method Status |
| *PlatformModelApi* | [**simulateLiveApplicationStatus**](docs/PlatformModelApi.md#simulateliveapplicationstatus) | **PATCH** /live_application/{merchant_id}/simulate_status | Live Application: Simulate Status |
| *PlatformModelApi* | [**submerchantSettlementCSV**](docs/PlatformModelApi.md#submerchantsettlementcsv) | **GET** /merchants/{merchant_id}/settlements/{id}/csv | Settlement: CSV |
| *PlatformModelApi* | [**submerchantSettlementPDF**](docs/PlatformModelApi.md#submerchantsettlementpdf) | **GET** /merchants/{merchant_id}/settlements/{id}/pdf | Settlement: PDF |
| *PlatformModelApi* | [**submerchantSettlementXLS**](docs/PlatformModelApi.md#submerchantsettlementxls) | **GET** /merchants/{merchant_id}/settlements/{id}/xls | Settlement: XLS |
| *PlatformModelApi* | [**updateLiveApplication**](docs/PlatformModelApi.md#updateliveapplication) | **PATCH** /live_application/{merchant_id} | Live Application: Update |
| *PlatformModelApi* | [**updateLiveApplicationPaymentMethod**](docs/PlatformModelApi.md#updateliveapplicationpaymentmethod) | **PATCH** /live_application/{merchant_id}/payment_methods/{payment_method} | Live Application: Update Payment Method |
| *PlatformModelApi* | [**updateMerchant**](docs/PlatformModelApi.md#updatemerchant) | **PATCH** /merchants/{id} | Merchant: Update |
| *SecureTokensApi* | [**createSecureToken**](docs/SecureTokensApi.md#createsecuretoken) | **POST** /secure_tokens | SecureToken: Create |
| *SecureTokensApi* | [**showSecureToken**](docs/SecureTokensApi.md#showsecuretoken) | **GET** /secure_tokens/{id} | SecureToken: Show |
| *SessionsApi* | [**cancelSession**](docs/SessionsApi.md#cancelsession) | **POST** /sessions/{id}/cancel | Session: Cancel |
| *SessionsApi* | [**createSession**](docs/SessionsApi.md#createsession) | **POST** /sessions | Session: Create |
| *SessionsApi* | [**paySession**](docs/SessionsApi.md#paysession) | **POST** /sessions/{id}/pay | Session: Pay |
| *SessionsApi* | [**showSession**](docs/SessionsApi.md#showsession) | **GET** /sessions/{id} | Session: Show |
| *SettlementsApi* | [**balanceTransactions**](docs/SettlementsApi.md#balancetransactions) | **GET** /balances/{currency}/transactions | Balance: Transactions |
| *SettlementsApi* | [**listSettlements**](docs/SettlementsApi.md#listsettlements) | **GET** /settlements | Settlement: Index |
| *SettlementsApi* | [**showBalance**](docs/SettlementsApi.md#showbalance) | **GET** /balances/{currency} | Balance: Show |
| *SettlementsApi* | [**showSettlement**](docs/SettlementsApi.md#showsettlement) | **GET** /settlements/{id} | Settlement: Show |
| *SettlementsApi* | [**showSettlementCSV**](docs/SettlementsApi.md#showsettlementcsv) | **GET** /settlements/{id}/csv | Settlement: CSV |
| *SettlementsApi* | [**showSettlementPDF**](docs/SettlementsApi.md#showsettlementpdf) | **GET** /settlements/{id}/pdf | Settlement: PDF |
| *SettlementsApi* | [**showSettlementXLS**](docs/SettlementsApi.md#showsettlementxls) | **GET** /settlements/{id}/xls | Settlement: XLS |
| *SettlementsApi* | [**showTransaction**](docs/SettlementsApi.md#showtransaction) | **GET** /balances/{currency}/transactions/{transaction_uuid} | Balance: Transaction |
| *SubscriptionsApi* | [**createCustomer**](docs/SubscriptionsApi.md#createcustomer) | **POST** /customers | Customer: Create |
| *SubscriptionsApi* | [**createSubscription**](docs/SubscriptionsApi.md#createsubscription) | **POST** /subscriptions | Subscription: Create |
| *SubscriptionsApi* | [**deleteCustomer**](docs/SubscriptionsApi.md#deletecustomer) | **DELETE** /customers/{id} | Customer: Destroy |
| *SubscriptionsApi* | [**deleteSubscription**](docs/SubscriptionsApi.md#deletesubscription) | **DELETE** /subscriptions/{id} | Subscription: Destroy |
| *SubscriptionsApi* | [**listCustomers**](docs/SubscriptionsApi.md#listcustomers) | **GET** /customers | Customer: List |
| *SubscriptionsApi* | [**listSubscriptions**](docs/SubscriptionsApi.md#listsubscriptions) | **GET** /subscriptions | Subscription: List |
| *SubscriptionsApi* | [**showCustomer**](docs/SubscriptionsApi.md#showcustomer) | **GET** /customers/{id} | Customer: Show |
| *SubscriptionsApi* | [**showSubscription**](docs/SubscriptionsApi.md#showsubscription) | **GET** /subscriptions/{id} | Subscription: Show |
| *SubscriptionsApi* | [**updateCustomer**](docs/SubscriptionsApi.md#updatecustomer) | **PATCH** /customers/{id} | Customer: Update |
| *TokensApi* | [**createToken**](docs/TokensApi.md#createtoken) | **POST** /tokens | Token: Create |


### Models

 - [APIError](docs/APIError.md)
 - [APIErrorBody](docs/APIErrorBody.md)
 - [Address](docs/Address.md)
 - [Auto](docs/Auto.md)
 - [AvailablePaymentMethod](docs/AvailablePaymentMethod.md)
 - [Balance](docs/Balance.md)
 - [BalanceSettings](docs/BalanceSettings.md)
 - [BalanceShow](docs/BalanceShow.md)
 - [BalanceTransactionList](docs/BalanceTransactionList.md)
 - [BalanceTransferRequest](docs/BalanceTransferRequest.md)
 - [BalanceTransferServiceRecord](docs/BalanceTransferServiceRecord.md)
 - [BarcodePendingResponse](docs/BarcodePendingResponse.md)
 - [BarcodeReadyResponse](docs/BarcodeReadyResponse.md)
 - [CancelDisbursementRequest](docs/CancelDisbursementRequest.md)
 - [CapturePaymentRequest](docs/CapturePaymentRequest.md)
 - [ChargebackCustomer](docs/ChargebackCustomer.md)
 - [ChargebackDefense](docs/ChargebackDefense.md)
 - [ChargebackDefenseDocument](docs/ChargebackDefenseDocument.md)
 - [ChargebackDefenseRecipientInfo](docs/ChargebackDefenseRecipientInfo.md)
 - [ChargebackDefenseShippingInfo](docs/ChargebackDefenseShippingInfo.md)
 - [ChargebackPayment](docs/ChargebackPayment.md)
 - [ChargebackPaymentMethod](docs/ChargebackPaymentMethod.md)
 - [ChargebackRequestDetail](docs/ChargebackRequestDetail.md)
 - [ChargebackRequestList](docs/ChargebackRequestList.md)
 - [ChargebackRequestListItem](docs/ChargebackRequestListItem.md)
 - [ChargebackStatus](docs/ChargebackStatus.md)
 - [ChargebackTimelineEntry](docs/ChargebackTimelineEntry.md)
 - [CountryCode](docs/CountryCode.md)
 - [CreateCustomerRequest](docs/CreateCustomerRequest.md)
 - [CreateDisbursementRequest](docs/CreateDisbursementRequest.md)
 - [CreateFileRequest](docs/CreateFileRequest.md)
 - [CreateMerchantBalanceTransferRequest](docs/CreateMerchantBalanceTransferRequest.md)
 - [CreateMerchantRequest](docs/CreateMerchantRequest.md)
 - [CreatePaymentRequest](docs/CreatePaymentRequest.md)
 - [CreatePaymentRequestWithCustomer](docs/CreatePaymentRequestWithCustomer.md)
 - [CreatePaymentRequestWithPaymentDetails](docs/CreatePaymentRequestWithPaymentDetails.md)
 - [CreatePaymentRequestWithPaymentDetailsTax](docs/CreatePaymentRequestWithPaymentDetailsTax.md)
 - [CreateRefundRequestRequest](docs/CreateRefundRequestRequest.md)
 - [CreateSecureTokenRequest](docs/CreateSecureTokenRequest.md)
 - [CreateSecureTokenRequestWithCustomer](docs/CreateSecureTokenRequestWithCustomer.md)
 - [CreateSecureTokenRequestWithPaymentDetails](docs/CreateSecureTokenRequestWithPaymentDetails.md)
 - [CreateSessionRequest](docs/CreateSessionRequest.md)
 - [CreateSessionRequestWithCustomerMode](docs/CreateSessionRequestWithCustomerMode.md)
 - [CreateSessionRequestWithCustomerPaymentMode](docs/CreateSessionRequestWithCustomerPaymentMode.md)
 - [CreateSessionRequestWithPaymentMode](docs/CreateSessionRequestWithPaymentMode.md)
 - [CreateSubscriptionRequest](docs/CreateSubscriptionRequest.md)
 - [CreateTokenRequest](docs/CreateTokenRequest.md)
 - [Currency](docs/Currency.md)
 - [Customer](docs/Customer.md)
 - [CustomerList](docs/CustomerList.md)
 - [CustomerSource](docs/CustomerSource.md)
 - [DefendChargebackDocument](docs/DefendChargebackDocument.md)
 - [DefendChargebackRecipientInfo](docs/DefendChargebackRecipientInfo.md)
 - [DefendChargebackRequestBody](docs/DefendChargebackRequestBody.md)
 - [DefendChargebackShippingInfo](docs/DefendChargebackShippingInfo.md)
 - [DeleteExternalCustomer200Response](docs/DeleteExternalCustomer200Response.md)
 - [Disbursement](docs/Disbursement.md)
 - [DisbursementList](docs/DisbursementList.md)
 - [DisbursementStatus](docs/DisbursementStatus.md)
 - [EditMerchantBalanceSettingsRequest](docs/EditMerchantBalanceSettingsRequest.md)
 - [ErroredField](docs/ErroredField.md)
 - [Event](docs/Event.md)
 - [EventList](docs/EventList.md)
 - [Field](docs/Field.md)
 - [FieldFieldProperties](docs/FieldFieldProperties.md)
 - [FinalizePaymentRequest](docs/FinalizePaymentRequest.md)
 - [FraudDetails](docs/FraudDetails.md)
 - [IndustryType](docs/IndustryType.md)
 - [Installments](docs/Installments.md)
 - [Intent](docs/Intent.md)
 - [LineItem](docs/LineItem.md)
 - [LiveApplication](docs/LiveApplication.md)
 - [LiveApplicationRequest](docs/LiveApplicationRequest.md)
 - [LiveApplicationStatus](docs/LiveApplicationStatus.md)
 - [LiveApplicationWithSubmittedFields](docs/LiveApplicationWithSubmittedFields.md)
 - [Locale](docs/Locale.md)
 - [MerchantBalance](docs/MerchantBalance.md)
 - [MerchantData](docs/MerchantData.md)
 - [MerchantFile](docs/MerchantFile.md)
 - [MerchantRole](docs/MerchantRole.md)
 - [MerchantSubmissionStatus](docs/MerchantSubmissionStatus.md)
 - [PaySessionRequest](docs/PaySessionRequest.md)
 - [PaySessionResponse](docs/PaySessionResponse.md)
 - [Payment](docs/Payment.md)
 - [PaymentData](docs/PaymentData.md)
 - [PaymentDataRequest](docs/PaymentDataRequest.md)
 - [PaymentDetailsAU](docs/PaymentDetailsAU.md)
 - [PaymentDetailsAlipay](docs/PaymentDetailsAlipay.md)
 - [PaymentDetailsAlipayHK](docs/PaymentDetailsAlipayHK.md)
 - [PaymentDetailsAll](docs/PaymentDetailsAll.md)
 - [PaymentDetailsAupay](docs/PaymentDetailsAupay.md)
 - [PaymentDetailsBancontact](docs/PaymentDetailsBancontact.md)
 - [PaymentDetailsBankTransfer](docs/PaymentDetailsBankTransfer.md)
 - [PaymentDetailsBitCash](docs/PaymentDetailsBitCash.md)
 - [PaymentDetailsBlik](docs/PaymentDetailsBlik.md)
 - [PaymentDetailsCVS](docs/PaymentDetailsCVS.md)
 - [PaymentDetailsCreditCard](docs/PaymentDetailsCreditCard.md)
 - [PaymentDetailsCreditCardBrazil](docs/PaymentDetailsCreditCardBrazil.md)
 - [PaymentDetailsCreditCardKorea](docs/PaymentDetailsCreditCardKorea.md)
 - [PaymentDetailsCreditCardKoreaSocialId](docs/PaymentDetailsCreditCardKoreaSocialId.md)
 - [PaymentDetailsCreditCardTerminal](docs/PaymentDetailsCreditCardTerminal.md)
 - [PaymentDetailsCultureVoucher](docs/PaymentDetailsCultureVoucher.md)
 - [PaymentDetailsDana](docs/PaymentDetailsDana.md)
 - [PaymentDetailsDocomo](docs/PaymentDetailsDocomo.md)
 - [PaymentDetailsDokuWallet](docs/PaymentDetailsDokuWallet.md)
 - [PaymentDetailsDospara](docs/PaymentDetailsDospara.md)
 - [PaymentDetailsDragonpay](docs/PaymentDetailsDragonpay.md)
 - [PaymentDetailsEnets](docs/PaymentDetailsEnets.md)
 - [PaymentDetailsEpospay](docs/PaymentDetailsEpospay.md)
 - [PaymentDetailsEps](docs/PaymentDetailsEps.md)
 - [PaymentDetailsFpx](docs/PaymentDetailsFpx.md)
 - [PaymentDetailsGCash](docs/PaymentDetailsGCash.md)
 - [PaymentDetailsGiropay](docs/PaymentDetailsGiropay.md)
 - [PaymentDetailsHappyMoney](docs/PaymentDetailsHappyMoney.md)
 - [PaymentDetailsIdeal](docs/PaymentDetailsIdeal.md)
 - [PaymentDetailsKakaopay](docs/PaymentDetailsKakaopay.md)
 - [PaymentDetailsKonbini](docs/PaymentDetailsKonbini.md)
 - [PaymentDetailsMerpay](docs/PaymentDetailsMerpay.md)
 - [PaymentDetailsMobile](docs/PaymentDetailsMobile.md)
 - [PaymentDetailsMobileJapan](docs/PaymentDetailsMobileJapan.md)
 - [PaymentDetailsMultibanco](docs/PaymentDetailsMultibanco.md)
 - [PaymentDetailsMybank](docs/PaymentDetailsMybank.md)
 - [PaymentDetailsNarvesen](docs/PaymentDetailsNarvesen.md)
 - [PaymentDetailsNaverpay](docs/PaymentDetailsNaverpay.md)
 - [PaymentDetailsNetCash](docs/PaymentDetailsNetCash.md)
 - [PaymentDetailsOnlyCreditCards](docs/PaymentDetailsOnlyCreditCards.md)
 - [PaymentDetailsOvo](docs/PaymentDetailsOvo.md)
 - [PaymentDetailsPaidy](docs/PaymentDetailsPaidy.md)
 - [PaymentDetailsPayEasy](docs/PaymentDetailsPayEasy.md)
 - [PaymentDetailsPayPay](docs/PaymentDetailsPayPay.md)
 - [PaymentDetailsPayco](docs/PaymentDetailsPayco.md)
 - [PaymentDetailsPaypost](docs/PaymentDetailsPaypost.md)
 - [PaymentDetailsPaysafeCard](docs/PaymentDetailsPaysafeCard.md)
 - [PaymentDetailsPaysafeCash](docs/PaymentDetailsPaysafeCash.md)
 - [PaymentDetailsPaysera](docs/PaymentDetailsPaysera.md)
 - [PaymentDetailsPayu](docs/PaymentDetailsPayu.md)
 - [PaymentDetailsPerlas](docs/PaymentDetailsPerlas.md)
 - [PaymentDetailsPix](docs/PaymentDetailsPix.md)
 - [PaymentDetailsPoli](docs/PaymentDetailsPoli.md)
 - [PaymentDetailsPrzelewy24](docs/PaymentDetailsPrzelewy24.md)
 - [PaymentDetailsRakutenpay](docs/PaymentDetailsRakutenpay.md)
 - [PaymentDetailsSepaTransfer](docs/PaymentDetailsSepaTransfer.md)
 - [PaymentDetailsSofortbanking](docs/PaymentDetailsSofortbanking.md)
 - [PaymentDetailsSoftbank](docs/PaymentDetailsSoftbank.md)
 - [PaymentDetailsTNG](docs/PaymentDetailsTNG.md)
 - [PaymentDetailsToss](docs/PaymentDetailsToss.md)
 - [PaymentDetailsTruemoney](docs/PaymentDetailsTruemoney.md)
 - [PaymentDetailsUnionpay](docs/PaymentDetailsUnionpay.md)
 - [PaymentDetailsWebMoney](docs/PaymentDetailsWebMoney.md)
 - [PaymentDetailsWechatpay](docs/PaymentDetailsWechatpay.md)
 - [PaymentList](docs/PaymentList.md)
 - [PaymentMethod](docs/PaymentMethod.md)
 - [PaymentMethodApplication](docs/PaymentMethodApplication.md)
 - [PaymentMethodApplicationStatus](docs/PaymentMethodApplicationStatus.md)
 - [PaymentMethodApplicationWithSubmittedFields](docs/PaymentMethodApplicationWithSubmittedFields.md)
 - [PaymentMethodBrands](docs/PaymentMethodBrands.md)
 - [PaymentMethodInstallmentsInner](docs/PaymentMethodInstallmentsInner.md)
 - [PaymentMethodStatus](docs/PaymentMethodStatus.md)
 - [PaymentMethodsList](docs/PaymentMethodsList.md)
 - [PaymentStatus](docs/PaymentStatus.md)
 - [PaymentType](docs/PaymentType.md)
 - [PlatformDetails](docs/PlatformDetails.md)
 - [PlatformMerchantPaymentList](docs/PlatformMerchantPaymentList.md)
 - [PlatformPayment](docs/PlatformPayment.md)
 - [PrepaidCards](docs/PrepaidCards.md)
 - [ProcessingMerchant](docs/ProcessingMerchant.md)
 - [Refund](docs/Refund.md)
 - [RefundPaymentRequest](docs/RefundPaymentRequest.md)
 - [RefundRequest](docs/RefundRequest.md)
 - [RefundRequestStatus](docs/RefundRequestStatus.md)
 - [ResponsePaymentDetailsAU](docs/ResponsePaymentDetailsAU.md)
 - [ResponsePaymentDetailsAlipay](docs/ResponsePaymentDetailsAlipay.md)
 - [ResponsePaymentDetailsAlipayHK](docs/ResponsePaymentDetailsAlipayHK.md)
 - [ResponsePaymentDetailsAll](docs/ResponsePaymentDetailsAll.md)
 - [ResponsePaymentDetailsAupay](docs/ResponsePaymentDetailsAupay.md)
 - [ResponsePaymentDetailsBancontact](docs/ResponsePaymentDetailsBancontact.md)
 - [ResponsePaymentDetailsBankTransfer](docs/ResponsePaymentDetailsBankTransfer.md)
 - [ResponsePaymentDetailsBitCash](docs/ResponsePaymentDetailsBitCash.md)
 - [ResponsePaymentDetailsBlik](docs/ResponsePaymentDetailsBlik.md)
 - [ResponsePaymentDetailsCVS](docs/ResponsePaymentDetailsCVS.md)
 - [ResponsePaymentDetailsCreditCard](docs/ResponsePaymentDetailsCreditCard.md)
 - [ResponsePaymentDetailsCreditCardBrazil](docs/ResponsePaymentDetailsCreditCardBrazil.md)
 - [ResponsePaymentDetailsCreditCardKorea](docs/ResponsePaymentDetailsCreditCardKorea.md)
 - [ResponsePaymentDetailsCreditCardTerminal](docs/ResponsePaymentDetailsCreditCardTerminal.md)
 - [ResponsePaymentDetailsCultureVoucher](docs/ResponsePaymentDetailsCultureVoucher.md)
 - [ResponsePaymentDetailsDana](docs/ResponsePaymentDetailsDana.md)
 - [ResponsePaymentDetailsDocomo](docs/ResponsePaymentDetailsDocomo.md)
 - [ResponsePaymentDetailsDokuWallet](docs/ResponsePaymentDetailsDokuWallet.md)
 - [ResponsePaymentDetailsDospara](docs/ResponsePaymentDetailsDospara.md)
 - [ResponsePaymentDetailsDragonpay](docs/ResponsePaymentDetailsDragonpay.md)
 - [ResponsePaymentDetailsEnets](docs/ResponsePaymentDetailsEnets.md)
 - [ResponsePaymentDetailsEpospay](docs/ResponsePaymentDetailsEpospay.md)
 - [ResponsePaymentDetailsEps](docs/ResponsePaymentDetailsEps.md)
 - [ResponsePaymentDetailsFpx](docs/ResponsePaymentDetailsFpx.md)
 - [ResponsePaymentDetailsGCash](docs/ResponsePaymentDetailsGCash.md)
 - [ResponsePaymentDetailsGiropay](docs/ResponsePaymentDetailsGiropay.md)
 - [ResponsePaymentDetailsHappyMoney](docs/ResponsePaymentDetailsHappyMoney.md)
 - [ResponsePaymentDetailsIdeal](docs/ResponsePaymentDetailsIdeal.md)
 - [ResponsePaymentDetailsKakaopay](docs/ResponsePaymentDetailsKakaopay.md)
 - [ResponsePaymentDetailsKonbini](docs/ResponsePaymentDetailsKonbini.md)
 - [ResponsePaymentDetailsMerpay](docs/ResponsePaymentDetailsMerpay.md)
 - [ResponsePaymentDetailsMobile](docs/ResponsePaymentDetailsMobile.md)
 - [ResponsePaymentDetailsMobileJapan](docs/ResponsePaymentDetailsMobileJapan.md)
 - [ResponsePaymentDetailsMultibanco](docs/ResponsePaymentDetailsMultibanco.md)
 - [ResponsePaymentDetailsMybank](docs/ResponsePaymentDetailsMybank.md)
 - [ResponsePaymentDetailsNarvesen](docs/ResponsePaymentDetailsNarvesen.md)
 - [ResponsePaymentDetailsNaverpay](docs/ResponsePaymentDetailsNaverpay.md)
 - [ResponsePaymentDetailsNetCash](docs/ResponsePaymentDetailsNetCash.md)
 - [ResponsePaymentDetailsOvo](docs/ResponsePaymentDetailsOvo.md)
 - [ResponsePaymentDetailsPaidy](docs/ResponsePaymentDetailsPaidy.md)
 - [ResponsePaymentDetailsPayEasy](docs/ResponsePaymentDetailsPayEasy.md)
 - [ResponsePaymentDetailsPayPay](docs/ResponsePaymentDetailsPayPay.md)
 - [ResponsePaymentDetailsPayco](docs/ResponsePaymentDetailsPayco.md)
 - [ResponsePaymentDetailsPaypost](docs/ResponsePaymentDetailsPaypost.md)
 - [ResponsePaymentDetailsPaysafeCard](docs/ResponsePaymentDetailsPaysafeCard.md)
 - [ResponsePaymentDetailsPaysafeCash](docs/ResponsePaymentDetailsPaysafeCash.md)
 - [ResponsePaymentDetailsPaysera](docs/ResponsePaymentDetailsPaysera.md)
 - [ResponsePaymentDetailsPayu](docs/ResponsePaymentDetailsPayu.md)
 - [ResponsePaymentDetailsPerlas](docs/ResponsePaymentDetailsPerlas.md)
 - [ResponsePaymentDetailsPix](docs/ResponsePaymentDetailsPix.md)
 - [ResponsePaymentDetailsPoli](docs/ResponsePaymentDetailsPoli.md)
 - [ResponsePaymentDetailsPrzelewy24](docs/ResponsePaymentDetailsPrzelewy24.md)
 - [ResponsePaymentDetailsRakutenpay](docs/ResponsePaymentDetailsRakutenpay.md)
 - [ResponsePaymentDetailsSepaTransfer](docs/ResponsePaymentDetailsSepaTransfer.md)
 - [ResponsePaymentDetailsSofortbanking](docs/ResponsePaymentDetailsSofortbanking.md)
 - [ResponsePaymentDetailsSoftbank](docs/ResponsePaymentDetailsSoftbank.md)
 - [ResponsePaymentDetailsTNG](docs/ResponsePaymentDetailsTNG.md)
 - [ResponsePaymentDetailsToss](docs/ResponsePaymentDetailsToss.md)
 - [ResponsePaymentDetailsTruemoney](docs/ResponsePaymentDetailsTruemoney.md)
 - [ResponsePaymentDetailsUnionpay](docs/ResponsePaymentDetailsUnionpay.md)
 - [ResponsePaymentDetailsWebMoney](docs/ResponsePaymentDetailsWebMoney.md)
 - [ResponsePaymentDetailsWechatpay](docs/ResponsePaymentDetailsWechatpay.md)
 - [SecureToken](docs/SecureToken.md)
 - [SecureTokenThreeDSecureAccount](docs/SecureTokenThreeDSecureAccount.md)
 - [SerializedSubmerchant](docs/SerializedSubmerchant.md)
 - [SerializedSubmerchantActivePaymentMethodsInner](docs/SerializedSubmerchantActivePaymentMethodsInner.md)
 - [SerializedSubmerchantExpirySettingsInner](docs/SerializedSubmerchantExpirySettingsInner.md)
 - [Session](docs/Session.md)
 - [SessionMode](docs/SessionMode.md)
 - [SessionStatus](docs/SessionStatus.md)
 - [Settlement](docs/Settlement.md)
 - [SettlementDownload](docs/SettlementDownload.md)
 - [SettlementFrequency](docs/SettlementFrequency.md)
 - [SettlementList](docs/SettlementList.md)
 - [SettlementShow](docs/SettlementShow.md)
 - [SharedDetails](docs/SharedDetails.md)
 - [SharedDetailsCorrections](docs/SharedDetailsCorrections.md)
 - [SharedDetailsDisbursements](docs/SharedDetailsDisbursements.md)
 - [SharedDetailsMisc](docs/SharedDetailsMisc.md)
 - [SharedDetailsPayments](docs/SharedDetailsPayments.md)
 - [SharedDetailsPlatformModel](docs/SharedDetailsPlatformModel.md)
 - [SharedDetailsRefunds](docs/SharedDetailsRefunds.md)
 - [ShowBalance200Response](docs/ShowBalance200Response.md)
 - [ShowBarcodeResponse](docs/ShowBarcodeResponse.md)
 - [SimulateLiveApplicationPaymentMethodStatusRequest](docs/SimulateLiveApplicationPaymentMethodStatusRequest.md)
 - [StatementDescriptor](docs/StatementDescriptor.md)
 - [Status](docs/Status.md)
 - [Submerchant](docs/Submerchant.md)
 - [SubmerchantListItem](docs/SubmerchantListItem.md)
 - [SubmerchantsList](docs/SubmerchantsList.md)
 - [SubmittedField](docs/SubmittedField.md)
 - [SubmittedFieldAllOfValue](docs/SubmittedFieldAllOfValue.md)
 - [Subscription](docs/Subscription.md)
 - [SubscriptionCustomer](docs/SubscriptionCustomer.md)
 - [SubscriptionList](docs/SubscriptionList.md)
 - [SubscriptionPaymentDetails](docs/SubscriptionPaymentDetails.md)
 - [SubscriptionPeriod](docs/SubscriptionPeriod.md)
 - [TerminalError](docs/TerminalError.md)
 - [TerminalErrorBody](docs/TerminalErrorBody.md)
 - [ThreeDsAuthResult](docs/ThreeDsAuthResult.md)
 - [Token](docs/Token.md)
 - [TokenPaymentDetails](docs/TokenPaymentDetails.md)
 - [Transaction](docs/Transaction.md)
 - [Transfer](docs/Transfer.md)
 - [UpdateCustomerRequest](docs/UpdateCustomerRequest.md)
 - [UpdateMerchantRequest](docs/UpdateMerchantRequest.md)
 - [UpdateMerchantRequestExpirySettingsInner](docs/UpdateMerchantRequestExpirySettingsInner.md)
 - [UpdatePaymentMethodRequest](docs/UpdatePaymentMethodRequest.md)
 - [UpdatePaymentRequest](docs/UpdatePaymentRequest.md)


### Authorization

KOMOJU uses HTTP Basic Auth. Use `config.setApiKey('your_key')` to authenticate — this sets the API key as the HTTP Basic username with an empty password.

### Building from Source

```
npm install
npm run build
```
