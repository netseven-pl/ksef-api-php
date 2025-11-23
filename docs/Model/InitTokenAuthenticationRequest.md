# # InitTokenAuthenticationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**challenge** | **string** | Wygenerowany wcześniej challenge. |
**context_identifier** | [**\NetSeven\KseF2Model\AuthenticationContextIdentifier**](AuthenticationContextIdentifier.md) | Indentyfikator kontekstu do którego następuje uwierzytelnienie. |
**encrypted_token** | **string** | Zaszyfrowany token wraz z timestampem z challenge&#39;a, w formacie &#x60;token|timestamp&#x60;. |
**authorization_policy** | [**\NetSeven\KseF2Model\AuthorizationPolicy**](AuthorizationPolicy.md) | Polityka autoryzacji żądań przy każdym użyciu tokena dostępu. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
