# # EntityAuthorizationGrant

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Identyfikator uprawnienia. |
**author_identifier** | [**\NetSeven\KseF2Model\EntityAuthorizationsAuthorIdentifier**](EntityAuthorizationsAuthorIdentifier.md) | Identyfikator osoby nadającej uprawnienie. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | | [optional]
**authorized_entity_identifier** | [**\NetSeven\KseF2Model\EntityAuthorizationsAuthorizedEntityIdentifier**](EntityAuthorizationsAuthorizedEntityIdentifier.md) | Identyfikator podmiotu uprawnionego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | PeppolId | Identyfikator dostawcy usług Peppol | |
**authorizing_entity_identifier** | [**\NetSeven\KseF2Model\EntityAuthorizationsAuthorizingEntityIdentifier**](EntityAuthorizationsAuthorizingEntityIdentifier.md) | Identyfikator podmiotu uprawniającego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | |
**authorization_scope** | [**\NetSeven\KseF2Model\InvoicePermissionType**](InvoicePermissionType.md) | Rodzaj uprawnienia. |
**description** | **string** | Opis uprawnienia. |
**start_date** | **\DateTime** | Data rozpoczęcia obowiązywania uprawnienia. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
