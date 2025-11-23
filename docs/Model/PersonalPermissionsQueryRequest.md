# # PersonalPermissionsQueryRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**context_identifier** | [**\NetSeven\KseF2Model\PersonalPermissionsContextIdentifier**](PersonalPermissionsContextIdentifier.md) | Identyfikator kontekstu podmiotu, który nadał uprawnienia do obsługi faktur. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | [optional]
**target_identifier** | [**\NetSeven\KseF2Model\PersonalPermissionsTargetIdentifier**](PersonalPermissionsTargetIdentifier.md) | Identyfikator podmiotu docelowego dla uprawnień selektywnych nadanych pośrednio. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | AllPartners | Identyfikator oznaczający, że wyszukiwanie dotyczy uprawnień generalnych nadanych w sposób pośredni | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**permission_types** | [**\NetSeven\KseF2Model\PersonalPermissionType[]**](PersonalPermissionType.md) | Lista rodzajów wyszukiwanych uprawnień. | [optional]
**permission_state** | [**\NetSeven\KseF2Model\PermissionState**](PermissionState.md) | Stan uprawnienia.  | Type | Value | | --- | --- | | Active | Uprawnienia aktywne | | Inactive | Uprawnienia nieaktywne | | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
