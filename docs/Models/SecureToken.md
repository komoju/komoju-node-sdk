# SecureToken

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **String** | A unique 25-character alphanumeric resource identifier. | [default to null] |
| **created\_at** | **Date** | Timestamp when the SecureToken was created. | [default to null] |
| **verification\_status** | **String** | Current 3DS verification status of this SecureToken. | [default to null] |
| **authentication\_url** | **String** | URL to redirect the customer to for 3DS authentication. Only present when verification_status is \&quot;NEEDS_VERIFY\&quot;. | [optional] [default to null] |
| **three\_d\_secure\_account** | [**SecureToken_three_d_secure_account**](SecureToken_three_d_secure_account.md) |  | [optional] [default to null] |
| **three\_ds\_auth\_result** | [**ThreeDsAuthResult**](ThreeDsAuthResult.md) |  | [optional] [default to null] |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#api-endpoints) [[Back to README]](../../README.md)

