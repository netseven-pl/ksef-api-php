# # SubunitPermissionsGrantRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subject_identifier** | [**\NetSeven\KseF2Model\SubunitPermissionsSubjectIdentifier**](SubunitPermissionsSubjectIdentifier.md) | Identyfikator podmiotu lub osoby fizycznej. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | Pesel | 11 cyfrowy numer PESEL | | Fingerprint | Odcisk palca certyfikatu | |
**context_identifier** | [**\NetSeven\KseF2Model\SubunitPermissionsContextIdentifier**](SubunitPermissionsContextIdentifier.md) | Identyfikator podmiotu podrzędnego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | InternalId | Dwuczłonowy identyfikator składający się z numeru NIP i 5 cyfr: &#x60;{nip}-{5_cyfr}&#x60; | |
**description** | **string** | Opis uprawnienia |
**subunit_name** | **string** | Nazwa jednostki podrzędnej. W przypadku jednostki podrzędnej z identyfikatorem wewnętrznym pole jest wymagane. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
