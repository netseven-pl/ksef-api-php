# # QueryTokensResponseItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**reference_number** | **string** | Numer referencyjny tokena KSeF. |
**author_identifier** | [**\NetSeven\KseF2Model\TokenAuthorIdentifierTypeIdentifier**](TokenAuthorIdentifierTypeIdentifier.md) | Identyfikator osoby która wygenerowała token. |
**context_identifier** | [**\NetSeven\KseF2Model\TokenContextIdentifierTypeIdentifier**](TokenContextIdentifierTypeIdentifier.md) | Identyfikator kontekstu, w którym został wygenerowany token i do którego daje dostęp. |
**description** | **string** | Opis tokena. |
**requested_permissions** | [**\NetSeven\KseF2Model\TokenPermissionType[]**](TokenPermissionType.md) | Uprawnienia przypisane tokenowi. |
**date_created** | **\DateTime** | Data i czas utworzenia tokena. |
**last_use_date** | **\DateTime** | Data ostatniego użycia tokena. | [optional]
**status** | [**\NetSeven\KseF2Model\AuthenticationTokenStatus**](AuthenticationTokenStatus.md) | Status tokena. | Wartość | Opis | | --- | --- | | Pending | Token został utworzony ale jest jeszcze w trakcie aktywacji i nadawania uprawnień. Nie może być jeszcze wykorzystywany do uwierzytelniania. | | Active | Token jest aktywny i może być wykorzystywany do uwierzytelniania. | | Revoking | Token jest w trakcie unieważniania. Nie może już być wykorzystywany do uwierzytelniania. | | Revoked | Token został unieważniony i nie może być wykorzystywany do uwierzytelniania. | | Failed | Nie udało się aktywować tokena. Należy wygenerować nowy token, obecny nie może być wykorzystywany do uwierzytelniania. | |
**status_details** | **string[]** | Dodatkowe informacje na temat statusu, zwracane w przypadku błędów. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
