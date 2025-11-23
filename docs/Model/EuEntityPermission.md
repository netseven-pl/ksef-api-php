# # EuEntityPermission

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Identyfikator uprawnienia. |
**author_identifier** | [**\NetSeven\KseF2Model\EuEntityPermissionsAuthorIdentifier**](EuEntityPermissionsAuthorIdentifier.md) | Identyfikator uprawniającego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**vat_ue_identifier** | **string** | Identyfikator podmiotu unijnego. |
**eu_entity_name** | **string** | Nazwa podmiotu unijnego. |
**authorized_fingerprint_identifier** | **string** | Uprawniony odcisk palca certyfikatu. |
**permission_scope** | [**\NetSeven\KseF2Model\EuEntityPermissionsQueryPermissionType**](EuEntityPermissionsQueryPermissionType.md) | Uprawnienie. |
**description** | **string** | Opis uprawnienia. |
**start_date** | **\DateTime** | Data rozpoczęcia obowiązywania uprawnienia. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
