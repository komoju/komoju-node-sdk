## @komoju/komoju-sdk @1.0.0-beta.1

TypeScript/JavaScript client for the KOMOJU API, using [axios](https://github.com/axios/axios).

### Installation

```
npm install @komoju/komoju-sdk@1.0.0-beta.1
```

### Getting Started

Get your API keys from the [KOMOJU Merchant Settings](https://komoju.com/merchant/settings).

#### TypeScript

```typescript
import { Configuration, PaymentsApi, SessionsApi } from '@komoju/komoju-sdk';

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

// Create a payment
const paymentsApi = new PaymentsApi(config);
const payment = await paymentsApi.createPayment({
  createPaymentRequest: {
    amount: 1000,
    currency: 'JPY',
    paymentDetails: {
      type: 'credit_card',
      number: '4111111111111111',
      month: 12,
      year: 2025,
      verificationValue: '123',
    },
  },
});
console.log('Payment created:', payment.data.id);

// Create a hosted payment page session
const sessionsApi = new SessionsApi(config);
const session = await sessionsApi.createSession({
  createSessionRequest: {
    amount: 5000,
    currency: 'JPY',
    returnUrl: 'https://example.com/thank-you',
    defaultLocale: 'ja',
  },
});
console.log('Redirect customer to:', session.data.sessionUrl);
```

#### JavaScript (CommonJS)

```javascript
const { Configuration, PaymentsApi, SessionsApi } = require('@komoju/komoju-sdk');

const config = new Configuration();
config.setApiKey('YOUR_SECRET_KEY');

const paymentsApi = new PaymentsApi(config);

paymentsApi
  .createPayment({
    createPaymentRequest: {
      amount: 1000,
      currency: 'JPY',
      paymentDetails: {
        type: 'credit_card',
        number: '4111111111111111',
        month: 12,
        year: 2025,
        verificationValue: '123',
      },
    },
  })
  .then((payment) => console.log('Payment created:', payment.data.id))
  .catch((error) => console.error('Error:', error));
```

### API Endpoints

All URIs are relative to *https://komoju.com/api/v1*

| Class | Method | HTTP request | Description |
|------------ | ------------- | ------------- | -------------|
| *BarcodesApi* | [**showBarcode**](docs/Apis/BarcodesApi.md#showbarcode) | **GET** /barcodes/{payment_id} | Barcode: Show |
| *DisbursementsApi* | [**cancelDisbursement**](docs/Apis/DisbursementsApi.md#canceldisbursement) | **POST** /disbursements/{id}/cancel | Disbursement: Cancel |
| *DisbursementsApi* | [**createDisbursement**](docs/Apis/DisbursementsApi.md#createdisbursement) | **POST** /disbursements | Disbursement: Create |
| *DisbursementsApi* | [**disbursementReport**](docs/Apis/DisbursementsApi.md#disbursementreport) | **GET** /disbursements/report | Disbursement: Report |
| *DisbursementsApi* | [**listDisbursements**](docs/Apis/DisbursementsApi.md#listdisbursements) | **GET** /disbursements | Disbursement: List |
| *DisbursementsApi* | [**showDisbursement**](docs/Apis/DisbursementsApi.md#showdisbursement) | **GET** /disbursements/{id} | Disbursement: Show |
| *EventsApi* | [**listEvents**](docs/Apis/EventsApi.md#listevents) | **GET** /events | Event: List |
| *EventsApi* | [**showEvent**](docs/Apis/EventsApi.md#showevent) | **GET** /events/{id} | Event Show |
| *OneClickApi* | [**deleteExternalCustomer**](docs/Apis/OneClickApi.md#deleteexternalcustomer) | **DELETE** /external_customers/{id} | External Customer: Destroy |
| *PaymentsApi* | [**cancelPayment**](docs/Apis/PaymentsApi.md#cancelpayment) | **POST** /payments/{id}/cancel | Payment: Cancel |
| *PaymentsApi* | [**capturePayment**](docs/Apis/PaymentsApi.md#capturepayment) | **POST** /payments/{id}/capture | Payment: Capture |
| *PaymentsApi* | [**createPayment**](docs/Apis/PaymentsApi.md#createpayment) | **POST** /payments | Payment: Create |
| *PaymentsApi* | [**createRefundRequest**](docs/Apis/PaymentsApi.md#createrefundrequest) | **POST** /payments/{id}/refund_request | Payment: Refund Request |
| *PaymentsApi* | [**finalizePayment**](docs/Apis/PaymentsApi.md#finalizepayment) | **POST** /payments/{id}/finalize | Payment: Finalize |
| *PaymentsApi* | [**listPaymentMethods**](docs/Apis/PaymentsApi.md#listpaymentmethods) | **GET** /payment_methods | Payment Method: List |
| *PaymentsApi* | [**listPayments**](docs/Apis/PaymentsApi.md#listpayments) | **GET** /payments | Payment: List |
| *PaymentsApi* | [**refundPayment**](docs/Apis/PaymentsApi.md#refundpayment) | **POST** /payments/{id}/refund | Payment: Refund |
| *PaymentsApi* | [**showPayment**](docs/Apis/PaymentsApi.md#showpayment) | **GET** /payments/{id} | Payment: Show |
| *PaymentsApi* | [**updatePayment**](docs/Apis/PaymentsApi.md#updatepayment) | **PATCH** /payments/{id} | Payment: Update |
| *PlatformModelApi* | [**balanceTransfer**](docs/Apis/PlatformModelApi.md#balancetransfer) | **POST** /balances/{currency}/transfer | Balance: Transfer |
| *PlatformModelApi* | [**createFile**](docs/Apis/PlatformModelApi.md#createfile) | **POST** /merchants/{merchant_id}/files | File: Create |
| *PlatformModelApi* | [**createMerchant**](docs/Apis/PlatformModelApi.md#createmerchant) | **POST** /merchants | Merchant: Create |
| *PlatformModelApi* | [**createMerchantBalanceTransfer**](docs/Apis/PlatformModelApi.md#createmerchantbalancetransfer) | **POST** /merchants/{merchant_id}/balances/{currency}/transfer | Balance: Transfer |
| *PlatformModelApi* | [**editMerchantBalanceSettings**](docs/Apis/PlatformModelApi.md#editmerchantbalancesettings) | **PATCH** /merchants/{merchant_id}/balances/{currency}/settings | Balances: Edit Settings |
| *PlatformModelApi* | [**listLiveApplicationPaymentMethods**](docs/Apis/PlatformModelApi.md#listliveapplicationpaymentmethods) | **GET** /live_application/{merchant_id}/payment_methods | Live Application: Payment Methods |
| *PlatformModelApi* | [**listMerchants**](docs/Apis/PlatformModelApi.md#listmerchants) | **GET** /merchants | Merchant: List |
| *PlatformModelApi* | [**listSubmerchantPayments**](docs/Apis/PlatformModelApi.md#listsubmerchantpayments) | **GET** /merchants/{merchant_id}/payments | Payment: List for Merchant |
| *PlatformModelApi* | [**listSubmerchantSettlements**](docs/Apis/PlatformModelApi.md#listsubmerchantsettlements) | **GET** /merchants/{merchant_id}/settlements | Settlement: List |
| *PlatformModelApi* | [**merchantBalanceTransactions**](docs/Apis/PlatformModelApi.md#merchantbalancetransactions) | **GET** /merchants/{merchant_id}/balances/{currency}/transactions | Balance: Transactions |
| *PlatformModelApi* | [**showFile**](docs/Apis/PlatformModelApi.md#showfile) | **GET** /merchants/{merchant_id}/files/{id} | File: Show |
| *PlatformModelApi* | [**showLiveApplication**](docs/Apis/PlatformModelApi.md#showliveapplication) | **GET** /live_application/{merchant_id} | Live Application: Show |
| *PlatformModelApi* | [**showLiveApplicationPaymentMethod**](docs/Apis/PlatformModelApi.md#showliveapplicationpaymentmethod) | **GET** /live_application/{merchant_id}/payment_methods/{payment_method} | Live Application: Show Payment Method |
| *PlatformModelApi* | [**showMerchant**](docs/Apis/PlatformModelApi.md#showmerchant) | **GET** /merchants/{id} | Merchant: Show |
| *PlatformModelApi* | [**showMerchantBalance**](docs/Apis/PlatformModelApi.md#showmerchantbalance) | **GET** /merchants/{merchant_id}/balances/{currency} | Balance: Show |
| *PlatformModelApi* | [**showMerchantBalanceSettings**](docs/Apis/PlatformModelApi.md#showmerchantbalancesettings) | **GET** /merchants/{merchant_id}/balances/{currency}/settings | Balance: Show Settings |
| *PlatformModelApi* | [**showMerchantBalanceTransaction**](docs/Apis/PlatformModelApi.md#showmerchantbalancetransaction) | **GET** /merchants/{merchant_id}/balances/{currency}/transactions/{transaction_uuid} | Balance: Transaction |
| *PlatformModelApi* | [**showSubmerchantSettlement**](docs/Apis/PlatformModelApi.md#showsubmerchantsettlement) | **GET** /merchants/{merchant_id}/settlements/{id} | Settlement: Show |
| *PlatformModelApi* | [**simulateLiveApplicationPaymentMethodStatus**](docs/Apis/PlatformModelApi.md#simulateliveapplicationpaymentmethodstatus) | **PATCH** /live_application/{merchant_id}/payment_methods/{payment_method}/simulate_status | Live Application: Simulate Payment Method Status |
| *PlatformModelApi* | [**simulateLiveApplicationStatus**](docs/Apis/PlatformModelApi.md#simulateliveapplicationstatus) | **PATCH** /live_application/{merchant_id}/simulate_status | Live Application: Simulate Status |
| *PlatformModelApi* | [**submerchantSettlementCSV**](docs/Apis/PlatformModelApi.md#submerchantsettlementcsv) | **GET** /merchants/{merchant_id}/settlements/{id}/csv | Settlement: CSV |
| *PlatformModelApi* | [**submerchantSettlementPDF**](docs/Apis/PlatformModelApi.md#submerchantsettlementpdf) | **GET** /merchants/{merchant_id}/settlements/{id}/pdf | Settlement: PDF |
| *PlatformModelApi* | [**submerchantSettlementXLS**](docs/Apis/PlatformModelApi.md#submerchantsettlementxls) | **GET** /merchants/{merchant_id}/settlements/{id}/xls | Settlement: XLS |
| *PlatformModelApi* | [**updateLiveApplication**](docs/Apis/PlatformModelApi.md#updateliveapplication) | **PATCH** /live_application/{merchant_id} | Live Application: Update |
| *PlatformModelApi* | [**updateLiveApplicationPaymentMethod**](docs/Apis/PlatformModelApi.md#updateliveapplicationpaymentmethod) | **PATCH** /live_application/{merchant_id}/payment_methods/{payment_method} | Live Application: Update Payment Method |
| *PlatformModelApi* | [**updateMerchant**](docs/Apis/PlatformModelApi.md#updatemerchant) | **PATCH** /merchants/{id} | Merchant: Update |
| *SecureTokensApi* | [**createSecureToken**](docs/Apis/SecureTokensApi.md#createsecuretoken) | **POST** /secure_tokens | SecureToken: Create |
| *SecureTokensApi* | [**showSecureToken**](docs/Apis/SecureTokensApi.md#showsecuretoken) | **GET** /secure_tokens/{id} | SecureToken: Show |
| *SessionsApi* | [**cancelSession**](docs/Apis/SessionsApi.md#cancelsession) | **POST** /sessions/{id}/cancel | Session: Cancel |
| *SessionsApi* | [**createSession**](docs/Apis/SessionsApi.md#createsession) | **POST** /sessions | Session: Create |
| *SessionsApi* | [**paySession**](docs/Apis/SessionsApi.md#paysession) | **POST** /sessions/{id}/pay | Session: Pay |
| *SessionsApi* | [**showSession**](docs/Apis/SessionsApi.md#showsession) | **GET** /sessions/{id} | Session: Show |
| *SettlementsApi* | [**listSettlements**](docs/Apis/SettlementsApi.md#listsettlements) | **GET** /settlements | Settlement: Index |
| *SettlementsApi* | [**showSettlement**](docs/Apis/SettlementsApi.md#showsettlement) | **GET** /settlements/{id} | Settlement: Show |
| *SettlementsApi* | [**showSettlementCSV**](docs/Apis/SettlementsApi.md#showsettlementcsv) | **GET** /settlements/{id}/csv | Settlement: CSV |
| *SettlementsApi* | [**showSettlementPDF**](docs/Apis/SettlementsApi.md#showsettlementpdf) | **GET** /settlements/{id}/pdf | Settlement: PDF |
| *SettlementsApi* | [**showSettlementXLS**](docs/Apis/SettlementsApi.md#showsettlementxls) | **GET** /settlements/{id}/xls | Settlement: XLS |
| *SettlementsApi* | [**showTransaction**](docs/Apis/SettlementsApi.md#showtransaction) | **GET** /balances/{currency}/transactions/{transaction_uuid} | Balance: Transaction |
| *SubscriptionsApi* | [**createCustomer**](docs/Apis/SubscriptionsApi.md#createcustomer) | **POST** /customers | Customer: Create |
| *SubscriptionsApi* | [**createSubscription**](docs/Apis/SubscriptionsApi.md#createsubscription) | **POST** /subscriptions | Subscription: Create |
| *SubscriptionsApi* | [**deleteCustomer**](docs/Apis/SubscriptionsApi.md#deletecustomer) | **DELETE** /customers/{id} | Customer: Destroy |
| *SubscriptionsApi* | [**deleteSubscription**](docs/Apis/SubscriptionsApi.md#deletesubscription) | **DELETE** /subscriptions/{id} | Subscription: Destroy |
| *SubscriptionsApi* | [**listCustomers**](docs/Apis/SubscriptionsApi.md#listcustomers) | **GET** /customers | Customer: List |
| *SubscriptionsApi* | [**listSubscriptions**](docs/Apis/SubscriptionsApi.md#listsubscriptions) | **GET** /subscriptions | Subscription: List |
| *SubscriptionsApi* | [**showCustomer**](docs/Apis/SubscriptionsApi.md#showcustomer) | **GET** /customers/{id} | Customer: Show |
| *SubscriptionsApi* | [**showSubscription**](docs/Apis/SubscriptionsApi.md#showsubscription) | **GET** /subscriptions/{id} | Subscription: Show |
| *SubscriptionsApi* | [**updateCustomer**](docs/Apis/SubscriptionsApi.md#updatecustomer) | **PATCH** /customers/{id} | Customer: Update |
| *TokensApi* | [**createToken**](docs/Apis/TokensApi.md#createtoken) | **POST** /tokens | Token: Create |


### Models

 - [APIError](docs/Models/APIError.md)
 - [APIErrorBody](docs/Models/APIErrorBody.md)
 - [Address](docs/Models/Address.md)
 - [Auto](docs/Models/Auto.md)
 - [AvailablePaymentMethod](docs/Models/AvailablePaymentMethod.md)
 - [Balance](docs/Models/Balance.md)
 - [BalanceSettings](docs/Models/BalanceSettings.md)
 - [BalanceShow](docs/Models/BalanceShow.md)
 - [BalanceTransactionList](docs/Models/BalanceTransactionList.md)
 - [BalanceTransferRequest](docs/Models/BalanceTransferRequest.md)
 - [BalanceTransferServiceRecord](docs/Models/BalanceTransferServiceRecord.md)
 - [BarcodePendingResponse](docs/Models/BarcodePendingResponse.md)
 - [BarcodeReadyResponse](docs/Models/BarcodeReadyResponse.md)
 - [CancelDisbursementRequest](docs/Models/CancelDisbursementRequest.md)
 - [CapturePaymentRequest](docs/Models/CapturePaymentRequest.md)
 - [CapturePaymentRequestTax](docs/Models/CapturePaymentRequestTax.md)
 - [CountryCode](docs/Models/CountryCode.md)
 - [CreateCustomerRequest](docs/Models/CreateCustomerRequest.md)
 - [CreateDisbursementRequest](docs/Models/CreateDisbursementRequest.md)
 - [CreateFileRequest](docs/Models/CreateFileRequest.md)
 - [CreateMerchantBalanceTransferRequest](docs/Models/CreateMerchantBalanceTransferRequest.md)
 - [CreateMerchantRequest](docs/Models/CreateMerchantRequest.md)
 - [CreatePaymentRequest](docs/Models/CreatePaymentRequest.md)
 - [CreatePaymentRequestWithCustomer](docs/Models/CreatePaymentRequestWithCustomer.md)
 - [CreatePaymentRequestWithPaymentDetails](docs/Models/CreatePaymentRequestWithPaymentDetails.md)
 - [CreatePaymentRequestWithPaymentDetailsTax](docs/Models/CreatePaymentRequestWithPaymentDetailsTax.md)
 - [CreateRefundRequestRequest](docs/Models/CreateRefundRequestRequest.md)
 - [CreateSecureTokenRequest](docs/Models/CreateSecureTokenRequest.md)
 - [CreateSecureTokenRequestWithCustomer](docs/Models/CreateSecureTokenRequestWithCustomer.md)
 - [CreateSecureTokenRequestWithPaymentDetails](docs/Models/CreateSecureTokenRequestWithPaymentDetails.md)
 - [CreateSessionRequest](docs/Models/CreateSessionRequest.md)
 - [CreateSessionRequestWithCustomerMode](docs/Models/CreateSessionRequestWithCustomerMode.md)
 - [CreateSessionRequestWithCustomerPaymentMode](docs/Models/CreateSessionRequestWithCustomerPaymentMode.md)
 - [CreateSessionRequestWithPaymentMode](docs/Models/CreateSessionRequestWithPaymentMode.md)
 - [CreateSubscriptionRequest](docs/Models/CreateSubscriptionRequest.md)
 - [CreateTokenRequest](docs/Models/CreateTokenRequest.md)
 - [Currency](docs/Models/Currency.md)
 - [Customer](docs/Models/Customer.md)
 - [CustomerList](docs/Models/CustomerList.md)
 - [CustomerSource](docs/Models/CustomerSource.md)
 - [DeleteExternalCustomerResponse](docs/Models/DeleteExternalCustomerResponse.md)
 - [Disbursement](docs/Models/Disbursement.md)
 - [DisbursementList](docs/Models/DisbursementList.md)
 - [DisbursementStatus](docs/Models/DisbursementStatus.md)
 - [EditMerchantBalanceSettingsRequest](docs/Models/EditMerchantBalanceSettingsRequest.md)
 - [ErroredField](docs/Models/ErroredField.md)
 - [Event](docs/Models/Event.md)
 - [EventList](docs/Models/EventList.md)
 - [Field](docs/Models/Field.md)
 - [FieldFieldProperties](docs/Models/FieldFieldProperties.md)
 - [FinalizePaymentRequest](docs/Models/FinalizePaymentRequest.md)
 - [FraudDetails](docs/Models/FraudDetails.md)
 - [IndustryType](docs/Models/IndustryType.md)
 - [Installments](docs/Models/Installments.md)
 - [Intent](docs/Models/Intent.md)
 - [LineItem](docs/Models/LineItem.md)
 - [LiveApplication](docs/Models/LiveApplication.md)
 - [LiveApplicationRequest](docs/Models/LiveApplicationRequest.md)
 - [LiveApplicationStatus](docs/Models/LiveApplicationStatus.md)
 - [LiveApplicationWithSubmittedFields](docs/Models/LiveApplicationWithSubmittedFields.md)
 - [Locale](docs/Models/Locale.md)
 - [MerchantBalance](docs/Models/MerchantBalance.md)
 - [MerchantData](docs/Models/MerchantData.md)
 - [MerchantFile](docs/Models/MerchantFile.md)
 - [MerchantRole](docs/Models/MerchantRole.md)
 - [MerchantSubmissionStatus](docs/Models/MerchantSubmissionStatus.md)
 - [PaySessionRequest](docs/Models/PaySessionRequest.md)
 - [PaySessionResponse](docs/Models/PaySessionResponse.md)
 - [Payment](docs/Models/Payment.md)
 - [PaymentData](docs/Models/PaymentData.md)
 - [PaymentDataRequest](docs/Models/PaymentDataRequest.md)
 - [PaymentDetailsAU](docs/Models/PaymentDetailsAU.md)
 - [PaymentDetailsAlipay](docs/Models/PaymentDetailsAlipay.md)
 - [PaymentDetailsAlipayHK](docs/Models/PaymentDetailsAlipayHK.md)
 - [PaymentDetailsAll](docs/Models/PaymentDetailsAll.md)
 - [PaymentDetailsAupay](docs/Models/PaymentDetailsAupay.md)
 - [PaymentDetailsBancontact](docs/Models/PaymentDetailsBancontact.md)
 - [PaymentDetailsBankTransfer](docs/Models/PaymentDetailsBankTransfer.md)
 - [PaymentDetailsBitCash](docs/Models/PaymentDetailsBitCash.md)
 - [PaymentDetailsBlik](docs/Models/PaymentDetailsBlik.md)
 - [PaymentDetailsCVS](docs/Models/PaymentDetailsCVS.md)
 - [PaymentDetailsCreditCard](docs/Models/PaymentDetailsCreditCard.md)
 - [PaymentDetailsCreditCardBrazil](docs/Models/PaymentDetailsCreditCardBrazil.md)
 - [PaymentDetailsCreditCardKorea](docs/Models/PaymentDetailsCreditCardKorea.md)
 - [PaymentDetailsCreditCardKoreaSocialId](docs/Models/PaymentDetailsCreditCardKoreaSocialId.md)
 - [PaymentDetailsCreditCardTerminal](docs/Models/PaymentDetailsCreditCardTerminal.md)
 - [PaymentDetailsCultureVoucher](docs/Models/PaymentDetailsCultureVoucher.md)
 - [PaymentDetailsDana](docs/Models/PaymentDetailsDana.md)
 - [PaymentDetailsDocomo](docs/Models/PaymentDetailsDocomo.md)
 - [PaymentDetailsDokuWallet](docs/Models/PaymentDetailsDokuWallet.md)
 - [PaymentDetailsDospara](docs/Models/PaymentDetailsDospara.md)
 - [PaymentDetailsDragonpay](docs/Models/PaymentDetailsDragonpay.md)
 - [PaymentDetailsEnets](docs/Models/PaymentDetailsEnets.md)
 - [PaymentDetailsEpospay](docs/Models/PaymentDetailsEpospay.md)
 - [PaymentDetailsEps](docs/Models/PaymentDetailsEps.md)
 - [PaymentDetailsFpx](docs/Models/PaymentDetailsFpx.md)
 - [PaymentDetailsGCash](docs/Models/PaymentDetailsGCash.md)
 - [PaymentDetailsGiropay](docs/Models/PaymentDetailsGiropay.md)
 - [PaymentDetailsHappyMoney](docs/Models/PaymentDetailsHappyMoney.md)
 - [PaymentDetailsIdeal](docs/Models/PaymentDetailsIdeal.md)
 - [PaymentDetailsKakaopay](docs/Models/PaymentDetailsKakaopay.md)
 - [PaymentDetailsKonbini](docs/Models/PaymentDetailsKonbini.md)
 - [PaymentDetailsMerpay](docs/Models/PaymentDetailsMerpay.md)
 - [PaymentDetailsMobile](docs/Models/PaymentDetailsMobile.md)
 - [PaymentDetailsMobileJapan](docs/Models/PaymentDetailsMobileJapan.md)
 - [PaymentDetailsMultibanco](docs/Models/PaymentDetailsMultibanco.md)
 - [PaymentDetailsMybank](docs/Models/PaymentDetailsMybank.md)
 - [PaymentDetailsNarvesen](docs/Models/PaymentDetailsNarvesen.md)
 - [PaymentDetailsNaverpay](docs/Models/PaymentDetailsNaverpay.md)
 - [PaymentDetailsNetCash](docs/Models/PaymentDetailsNetCash.md)
 - [PaymentDetailsOnlyCreditCards](docs/Models/PaymentDetailsOnlyCreditCards.md)
 - [PaymentDetailsOvo](docs/Models/PaymentDetailsOvo.md)
 - [PaymentDetailsPaidy](docs/Models/PaymentDetailsPaidy.md)
 - [PaymentDetailsPayEasy](docs/Models/PaymentDetailsPayEasy.md)
 - [PaymentDetailsPayPay](docs/Models/PaymentDetailsPayPay.md)
 - [PaymentDetailsPayco](docs/Models/PaymentDetailsPayco.md)
 - [PaymentDetailsPaypost](docs/Models/PaymentDetailsPaypost.md)
 - [PaymentDetailsPaysafeCard](docs/Models/PaymentDetailsPaysafeCard.md)
 - [PaymentDetailsPaysafeCash](docs/Models/PaymentDetailsPaysafeCash.md)
 - [PaymentDetailsPaysera](docs/Models/PaymentDetailsPaysera.md)
 - [PaymentDetailsPayu](docs/Models/PaymentDetailsPayu.md)
 - [PaymentDetailsPerlas](docs/Models/PaymentDetailsPerlas.md)
 - [PaymentDetailsPix](docs/Models/PaymentDetailsPix.md)
 - [PaymentDetailsPoli](docs/Models/PaymentDetailsPoli.md)
 - [PaymentDetailsPrzelewy24](docs/Models/PaymentDetailsPrzelewy24.md)
 - [PaymentDetailsRakutenpay](docs/Models/PaymentDetailsRakutenpay.md)
 - [PaymentDetailsSepaTransfer](docs/Models/PaymentDetailsSepaTransfer.md)
 - [PaymentDetailsSofortbanking](docs/Models/PaymentDetailsSofortbanking.md)
 - [PaymentDetailsSoftbank](docs/Models/PaymentDetailsSoftbank.md)
 - [PaymentDetailsTNG](docs/Models/PaymentDetailsTNG.md)
 - [PaymentDetailsToss](docs/Models/PaymentDetailsToss.md)
 - [PaymentDetailsTruemoney](docs/Models/PaymentDetailsTruemoney.md)
 - [PaymentDetailsUnionpay](docs/Models/PaymentDetailsUnionpay.md)
 - [PaymentDetailsWebMoney](docs/Models/PaymentDetailsWebMoney.md)
 - [PaymentDetailsWechatpay](docs/Models/PaymentDetailsWechatpay.md)
 - [PaymentList](docs/Models/PaymentList.md)
 - [PaymentMethod](docs/Models/PaymentMethod.md)
 - [PaymentMethodBrands](docs/Models/PaymentMethodBrands.md)
 - [PaymentMethodInstallmentsInner](docs/Models/PaymentMethodInstallmentsInner.md)
 - [PaymentMethodStatus](docs/Models/PaymentMethodStatus.md)
 - [PaymentMethodsList](docs/Models/PaymentMethodsList.md)
 - [PaymentStatus](docs/Models/PaymentStatus.md)
 - [PaymentType](docs/Models/PaymentType.md)
 - [PlatformDetails](docs/Models/PlatformDetails.md)
 - [PlatformMerchantPaymentList](docs/Models/PlatformMerchantPaymentList.md)
 - [PlatformPayment](docs/Models/PlatformPayment.md)
 - [PrepaidCards](docs/Models/PrepaidCards.md)
 - [ProcessingMerchant](docs/Models/ProcessingMerchant.md)
 - [Refund](docs/Models/Refund.md)
 - [RefundPaymentRequest](docs/Models/RefundPaymentRequest.md)
 - [RefundRequest](docs/Models/RefundRequest.md)
 - [RefundRequestStatus](docs/Models/RefundRequestStatus.md)
 - [ResponsePaymentDetailsAU](docs/Models/ResponsePaymentDetailsAU.md)
 - [ResponsePaymentDetailsAlipay](docs/Models/ResponsePaymentDetailsAlipay.md)
 - [ResponsePaymentDetailsAlipayHK](docs/Models/ResponsePaymentDetailsAlipayHK.md)
 - [ResponsePaymentDetailsAll](docs/Models/ResponsePaymentDetailsAll.md)
 - [ResponsePaymentDetailsAupay](docs/Models/ResponsePaymentDetailsAupay.md)
 - [ResponsePaymentDetailsBancontact](docs/Models/ResponsePaymentDetailsBancontact.md)
 - [ResponsePaymentDetailsBankTransfer](docs/Models/ResponsePaymentDetailsBankTransfer.md)
 - [ResponsePaymentDetailsBitCash](docs/Models/ResponsePaymentDetailsBitCash.md)
 - [ResponsePaymentDetailsBlik](docs/Models/ResponsePaymentDetailsBlik.md)
 - [ResponsePaymentDetailsCVS](docs/Models/ResponsePaymentDetailsCVS.md)
 - [ResponsePaymentDetailsCreditCard](docs/Models/ResponsePaymentDetailsCreditCard.md)
 - [ResponsePaymentDetailsCreditCardBrazil](docs/Models/ResponsePaymentDetailsCreditCardBrazil.md)
 - [ResponsePaymentDetailsCreditCardKorea](docs/Models/ResponsePaymentDetailsCreditCardKorea.md)
 - [ResponsePaymentDetailsCreditCardTerminal](docs/Models/ResponsePaymentDetailsCreditCardTerminal.md)
 - [ResponsePaymentDetailsCultureVoucher](docs/Models/ResponsePaymentDetailsCultureVoucher.md)
 - [ResponsePaymentDetailsDana](docs/Models/ResponsePaymentDetailsDana.md)
 - [ResponsePaymentDetailsDocomo](docs/Models/ResponsePaymentDetailsDocomo.md)
 - [ResponsePaymentDetailsDokuWallet](docs/Models/ResponsePaymentDetailsDokuWallet.md)
 - [ResponsePaymentDetailsDospara](docs/Models/ResponsePaymentDetailsDospara.md)
 - [ResponsePaymentDetailsDragonpay](docs/Models/ResponsePaymentDetailsDragonpay.md)
 - [ResponsePaymentDetailsEnets](docs/Models/ResponsePaymentDetailsEnets.md)
 - [ResponsePaymentDetailsEpospay](docs/Models/ResponsePaymentDetailsEpospay.md)
 - [ResponsePaymentDetailsEps](docs/Models/ResponsePaymentDetailsEps.md)
 - [ResponsePaymentDetailsFpx](docs/Models/ResponsePaymentDetailsFpx.md)
 - [ResponsePaymentDetailsGCash](docs/Models/ResponsePaymentDetailsGCash.md)
 - [ResponsePaymentDetailsGiropay](docs/Models/ResponsePaymentDetailsGiropay.md)
 - [ResponsePaymentDetailsHappyMoney](docs/Models/ResponsePaymentDetailsHappyMoney.md)
 - [ResponsePaymentDetailsIdeal](docs/Models/ResponsePaymentDetailsIdeal.md)
 - [ResponsePaymentDetailsKakaopay](docs/Models/ResponsePaymentDetailsKakaopay.md)
 - [ResponsePaymentDetailsKonbini](docs/Models/ResponsePaymentDetailsKonbini.md)
 - [ResponsePaymentDetailsMerpay](docs/Models/ResponsePaymentDetailsMerpay.md)
 - [ResponsePaymentDetailsMobile](docs/Models/ResponsePaymentDetailsMobile.md)
 - [ResponsePaymentDetailsMobileJapan](docs/Models/ResponsePaymentDetailsMobileJapan.md)
 - [ResponsePaymentDetailsMultibanco](docs/Models/ResponsePaymentDetailsMultibanco.md)
 - [ResponsePaymentDetailsMybank](docs/Models/ResponsePaymentDetailsMybank.md)
 - [ResponsePaymentDetailsNarvesen](docs/Models/ResponsePaymentDetailsNarvesen.md)
 - [ResponsePaymentDetailsNaverpay](docs/Models/ResponsePaymentDetailsNaverpay.md)
 - [ResponsePaymentDetailsNetCash](docs/Models/ResponsePaymentDetailsNetCash.md)
 - [ResponsePaymentDetailsOvo](docs/Models/ResponsePaymentDetailsOvo.md)
 - [ResponsePaymentDetailsPaidy](docs/Models/ResponsePaymentDetailsPaidy.md)
 - [ResponsePaymentDetailsPayEasy](docs/Models/ResponsePaymentDetailsPayEasy.md)
 - [ResponsePaymentDetailsPayPay](docs/Models/ResponsePaymentDetailsPayPay.md)
 - [ResponsePaymentDetailsPayco](docs/Models/ResponsePaymentDetailsPayco.md)
 - [ResponsePaymentDetailsPaypost](docs/Models/ResponsePaymentDetailsPaypost.md)
 - [ResponsePaymentDetailsPaysafeCard](docs/Models/ResponsePaymentDetailsPaysafeCard.md)
 - [ResponsePaymentDetailsPaysafeCash](docs/Models/ResponsePaymentDetailsPaysafeCash.md)
 - [ResponsePaymentDetailsPaysera](docs/Models/ResponsePaymentDetailsPaysera.md)
 - [ResponsePaymentDetailsPayu](docs/Models/ResponsePaymentDetailsPayu.md)
 - [ResponsePaymentDetailsPerlas](docs/Models/ResponsePaymentDetailsPerlas.md)
 - [ResponsePaymentDetailsPix](docs/Models/ResponsePaymentDetailsPix.md)
 - [ResponsePaymentDetailsPoli](docs/Models/ResponsePaymentDetailsPoli.md)
 - [ResponsePaymentDetailsPrzelewy24](docs/Models/ResponsePaymentDetailsPrzelewy24.md)
 - [ResponsePaymentDetailsRakutenpay](docs/Models/ResponsePaymentDetailsRakutenpay.md)
 - [ResponsePaymentDetailsSepaTransfer](docs/Models/ResponsePaymentDetailsSepaTransfer.md)
 - [ResponsePaymentDetailsSofortbanking](docs/Models/ResponsePaymentDetailsSofortbanking.md)
 - [ResponsePaymentDetailsSoftbank](docs/Models/ResponsePaymentDetailsSoftbank.md)
 - [ResponsePaymentDetailsTNG](docs/Models/ResponsePaymentDetailsTNG.md)
 - [ResponsePaymentDetailsToss](docs/Models/ResponsePaymentDetailsToss.md)
 - [ResponsePaymentDetailsTruemoney](docs/Models/ResponsePaymentDetailsTruemoney.md)
 - [ResponsePaymentDetailsUnionpay](docs/Models/ResponsePaymentDetailsUnionpay.md)
 - [ResponsePaymentDetailsWebMoney](docs/Models/ResponsePaymentDetailsWebMoney.md)
 - [ResponsePaymentDetailsWechatpay](docs/Models/ResponsePaymentDetailsWechatpay.md)
 - [SecureToken](docs/Models/SecureToken.md)
 - [SerializedSubmerchant](docs/Models/SerializedSubmerchant.md)
 - [SerializedSubmerchantActivePaymentMethodsInner](docs/Models/SerializedSubmerchantActivePaymentMethodsInner.md)
 - [SerializedSubmerchantExpirySettingsInner](docs/Models/SerializedSubmerchantExpirySettingsInner.md)
 - [Session](docs/Models/Session.md)
 - [SessionMode](docs/Models/SessionMode.md)
 - [SessionStatus](docs/Models/SessionStatus.md)
 - [Settlement](docs/Models/Settlement.md)
 - [SettlementDownload](docs/Models/SettlementDownload.md)
 - [SettlementFrequency](docs/Models/SettlementFrequency.md)
 - [SettlementList](docs/Models/SettlementList.md)
 - [SettlementShow](docs/Models/SettlementShow.md)
 - [SharedDetails](docs/Models/SharedDetails.md)
 - [SharedDetailsCorrections](docs/Models/SharedDetailsCorrections.md)
 - [SharedDetailsDisbursements](docs/Models/SharedDetailsDisbursements.md)
 - [SharedDetailsMisc](docs/Models/SharedDetailsMisc.md)
 - [SharedDetailsPayments](docs/Models/SharedDetailsPayments.md)
 - [SharedDetailsPlatformModel](docs/Models/SharedDetailsPlatformModel.md)
 - [SharedDetailsRefunds](docs/Models/SharedDetailsRefunds.md)
 - [ShowBarcodeResponse](docs/Models/ShowBarcodeResponse.md)
 - [SimulateLiveApplicationPaymentMethodStatusRequest](docs/Models/SimulateLiveApplicationPaymentMethodStatusRequest.md)
 - [StatementDescriptor](docs/Models/StatementDescriptor.md)
 - [Status](docs/Models/Status.md)
 - [Submerchant](docs/Models/Submerchant.md)
 - [SubmerchantListItem](docs/Models/SubmerchantListItem.md)
 - [SubmerchantsList](docs/Models/SubmerchantsList.md)
 - [SubmittedField](docs/Models/SubmittedField.md)
 - [SubmittedFieldAllOfValue](docs/Models/SubmittedFieldAllOfValue.md)
 - [Subscription](docs/Models/Subscription.md)
 - [SubscriptionCustomer](docs/Models/SubscriptionCustomer.md)
 - [SubscriptionList](docs/Models/SubscriptionList.md)
 - [SubscriptionPaymentDetails](docs/Models/SubscriptionPaymentDetails.md)
 - [SubscriptionPeriod](docs/Models/SubscriptionPeriod.md)
 - [TerminalError](docs/Models/TerminalError.md)
 - [TerminalErrorBody](docs/Models/TerminalErrorBody.md)
 - [ThreeDsAuthResult](docs/Models/ThreeDsAuthResult.md)
 - [Token](docs/Models/Token.md)
 - [TokenPaymentDetails](docs/Models/TokenPaymentDetails.md)
 - [Transaction](docs/Models/Transaction.md)
 - [Transfer](docs/Models/Transfer.md)
 - [UpdateCustomerRequest](docs/Models/UpdateCustomerRequest.md)
 - [UpdateMerchantRequest](docs/Models/UpdateMerchantRequest.md)
 - [UpdateMerchantRequestExpirySettingsInner](docs/Models/UpdateMerchantRequestExpirySettingsInner.md)
 - [UpdatePaymentMethodRequest](docs/Models/UpdatePaymentMethodRequest.md)
 - [UpdatePaymentRequest](docs/Models/UpdatePaymentRequest.md)


### Authorization

KOMOJU uses HTTP Basic Auth. Use `config.setApiKey('your_key')` to authenticate — this sets the API key as the HTTP Basic username with an empty password.

### Building from Source

```
npm install
npm run build
```
