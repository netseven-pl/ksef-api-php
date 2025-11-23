# # PersonPermissionsQueryRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**author_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsAuthorIdentifier**](PersonPermissionsAuthorIdentifier.md) | Identyfikator osoby lub podmiotu nadającego uprawnienie. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | | System | Identyfikator systemowy KSeF | | [optional]
**authorized_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsAuthorizedIdentifier**](PersonPermissionsAuthorizedIdentifier.md) | Identyfikator osoby lub podmiotu uprawnionego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | | [optional]
**context_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsContextIdentifier**](PersonPermissionsContextIdentifier.md) | Identyfikator kontekstu uprawnienia (dla uprawnień nadanych administratorom jednostek podrzędnych). | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**target_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsTargetIdentifier**](PersonPermissionsTargetIdentifier.md) | Identyfikator podmiotu docelowego dla uprawnień nadanych pośrednio. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | AllPartners | Identyfikator oznaczający, że uprawnienie nadane w sposób pośredni jest typu generalnego | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**permission_types** | [**\NetSeven\KseF2Model\PersonPermissionType[]**](PersonPermissionType.md) | Lista rodzajów wyszukiwanych uprawnień. | [optional]
**permission_state** | [**\NetSeven\KseF2Model\PermissionState**](PermissionState.md) | Stan uprawnienia.  | Type | Value | | --- | --- | | Active | Uprawnienia aktywne | | Inactive | Uprawnienia nieaktywne, nadane w sposób poœredni | | [optional]
**query_type** | [**\NetSeven\KseF2Model\PersonPermissionsQueryType**](PersonPermissionsQueryType.md) | Typ zapytania. | Type | Value | | --- | --- | | PermissionsInCurrentContext | Lista uprawnień obowiązujących w bieżącym kontekście | | PermissionsGrantedInCurrentContext | Lista uprawmoeń nadanych w bieżącym kontekście | |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
