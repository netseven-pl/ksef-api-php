# # PersonPermissionsGrantRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subject_identifier** | [**\NetSeven\KseF2Model\PersonPermissionsSubjectIdentifier**](PersonPermissionsSubjectIdentifier.md) | Identyfikator osoby fizycznej. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**permissions** | [**\NetSeven\KseF2Model\PersonPermissionType[]**](PersonPermissionType.md) | Lista nadawanych uprawnień. Każda wartość może wystąpić tylko raz. |
**description** | **string** | Opis uprawnienia |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
