# # SubunitPermission

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Identyfikator uprawnienia. |
**authorized_identifier** | [**\NetSeven\KseF2Model\SubunitPermissionsAuthorizedIdentifier**](SubunitPermissionsAuthorizedIdentifier.md) | Identyfikator uprawnionego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**subunit_identifier** | [**\NetSeven\KseF2Model\SubunitPermissionsSubunitIdentifier**](SubunitPermissionsSubunitIdentifier.md) | Identyfikator jednostki lub podmiotu podrzędnego. | Type | Value | | --- | --- | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | Nip | 10 cyfrowy numer NIP | |
**author_identifier** | [**\NetSeven\KseF2Model\SubunitPermissionsAuthorIdentifier**](SubunitPermissionsAuthorIdentifier.md) | Identyfikator uprawniającego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**permission_scope** | [**\NetSeven\KseF2Model\SubunitPermissionScope**](SubunitPermissionScope.md) | Rodzaj uprawnienia. |
**description** | **string** | Opis uprawnienia. |
**subunit_name** | **string** | Nazwa jednostki podrzędnej. | [optional]
**start_date** | **\DateTime** | Data rozpoczęcia obowiązywania uprawnienia. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
