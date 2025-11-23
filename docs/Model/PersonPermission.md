# # PersonPermission

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Identyfikator uprawnienia. |
**authorized_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsAuthorizedIdentifier**](PersonPermissionsAuthorizedIdentifier.md) | Identyfikator osoby lub podmiotu uprawnionego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**context_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsContextIdentifier**](PersonPermissionsContextIdentifier.md) | Identyfikator kontekstu uprawnienia (dla uprawnień nadanych administratorom jednostek podrzędnych). | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**target_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsTargetIdentifier**](PersonPermissionsTargetIdentifier.md) | Identyfikator podmiotu docelowego dla uprawnień nadanych pośrednio. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | AllPartners | Identyfikator oznaczający, że uprawnienie nadane w sposób pośredni jest typu generalnego | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**author_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsAuthorIdentifier**](PersonPermissionsAuthorIdentifier.md) | Identyfikator osoby lub podmiotu nadającego uprawnienie. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | | System | Identyfikator systemowy KSeF | |
**permission_scope** | [**\NetSeven\KseF2Model\PersonPermissionScope**](PersonPermissionScope.md) | Rodzaj uprawnienia. |
**description** | **string** | Opis uprawnienia. |
**permission_state** | [**\NetSeven\KseF2Model\PermissionState**](PermissionState.md) | Stan uprawnienia. |
**start_date** | **\DateTime** | Data rozpoczęcia obowiązywania uprawnienia. |
**can_delegate** | **bool** | Flaga określająca, czy uprawnienie ma być możliwe do dalszego przekazywania. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
