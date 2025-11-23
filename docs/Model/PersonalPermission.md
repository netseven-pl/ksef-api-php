# # PersonalPermission

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Identyfikator uprawnienia. |
**context_identifier** | [**\NetSeven\KseF2Model\PersonalPermissionsContextIdentifier**](PersonalPermissionsContextIdentifier.md) | Identyfikator kontekstu podmiotu, który nadał uprawnienia do obsługi faktur. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | [optional]
**authorized_identifier** | [**\NetSeven\KseF2Model\PersonalPermissionsAuthorizedIdentifier**](PersonalPermissionsAuthorizedIdentifier.md) | Identyfikator podmiotu uprawnionego, jeżeli jest inny niż identyfikator uwierzytelnionego klienta API. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | [optional]
**target_identifier** | [**\NetSeven\KseF2Model\PersonalPermissionsTargetIdentifier**](PersonalPermissionsTargetIdentifier.md) | Identyfikator podmiotu docelowego dla uprawnień selektywnych nadanych pośrednio. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | AllPartners | Identyfikator oznaczający, że wyszukiwanie dotyczy uprawnień generalnych nadanych w sposób pośredni | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**permission_scope** | [**\NetSeven\KseF2Model\PersonalPermissionScope**](PersonalPermissionScope.md) | Rodzaj uprawnienia. |
**description** | **string** | Opis uprawnienia. |
**permission_state** | [**\NetSeven\KseF2Model\PermissionState**](PermissionState.md) | Stan uprawnienia. |
**start_date** | **\DateTime** | Data rozpoczęcia obowiązywania uprawnienia. |
**can_delegate** | **bool** | Flaga określająca, czy uprawnienie ma być możliwe do dalszego przekazywania. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
