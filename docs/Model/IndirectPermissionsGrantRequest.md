# # IndirectPermissionsGrantRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subject_identifier** | [**\NetSeven\KseF2Model\IndirectPermissionsSubjectIdentifier**](IndirectPermissionsSubjectIdentifier.md) | Identyfikator osoby fizycznej. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**target_identifier** | [**\NetSeven\KseF2Model\IndirectPermissionsTargetIdentifier**](IndirectPermissionsTargetIdentifier.md) | Identyfikator kontekstu klienta. Nie przekazanie identyfikatora oznacza, że uprawnienie nadane w sposób pośredni jest typu generalnego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | AllPartners | Identyfikator oznaczający, że uprawnienie nadane w sposób pośredni jest typu generalnego | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | | [optional]
**permissions** | [**\NetSeven\KseF2Model\IndirectPermissionType[]**](IndirectPermissionType.md) | Lista nadawanych uprawnień. Każda wartość może wystąpić tylko raz. |
**description** | **string** | Opis uprawnienia |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
