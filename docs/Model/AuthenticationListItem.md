# # AuthenticationListItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**start_date** | **\DateTime** | Data rozpoczęcia operacji uwierzytelnienia. |
**authentication_method** | [**\NetSeven\KseF2Model\AuthenticationMethod**](AuthenticationMethod.md) | Metoda uwierzytelnienia. | Wartość | Opis | | --- | --- | | Token | Token KSeF. | | TrustedProfile | Profil Zaufany. | | InternalCertificate | Certyfikat KSeF. | | QualifiedSignature | Podpis kwalifikowany. | | QualifiedSeal | Pieczęć kwalifikowana. | | PersonalSignature | Podpis osobisty. | | PeppolSignature | Podpis dostawcy uslug Peppol. | |
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Informacje o aktualnym statusie. | Code | Description | Details | | --- | --- | --- | | 100 | Uwierzytelnianie w toku | - | | 200 | Uwierzytelnianie zakończone sukcesem | - | | 415 | Uwierzytelnianie zakończone niepowodzeniem | Brak przypisanych uprawnień | | 425 | Uwierzytelnienie unieważnione  | Uwierzytelnienie i powiązane refresh tokeny zostały unieważnione przez użytkownika | | 450 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędnego tokenu | Nieprawidłowy token | | 450 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędnego tokenu | Nieprawidłowy czas tokena | | 450 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędnego tokenu | Token unieważniony | | 450 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędnego tokenu | Token nieaktywny | | 460 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędu certyfikatu | Nieważny certyfikat | | 460 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędu certyfikatu | Błąd weryfikacji łańcucha certyfikatów | | 460 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędu certyfikatu | Niezaufany łańcuch certyfikatów | | 460 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędu certyfikatu | Certyfikat odwołany | | 460 | Uwierzytelnianie zakończone niepowodzeniem z powodu błędu certyfikatu | Niepoprawny certyfikat | | 470 | Uwierzytelnianie zakończone niepowodzeniem | Próba wykorzystania metod autoryzacyjnych osoby zmarłej | | 500 | Nieznany błąd | - | | 550 | Operacja została anulowana przez system | Przetwarzanie zostało przerwane z przyczyn wewnętrznych systemu. Spróbuj ponownie | |
**is_token_redeemed** | **bool** | Czy został już wydany refresh token powiązany z danym uwierzytelnieniem. | [optional]
**last_token_refresh_date** | **\DateTime** | Data ostatniego odświeżenia tokena. | [optional]
**refresh_token_valid_until** | **\DateTime** | Termin ważności refresh tokena (o ile nie zostanie wcześniej unieważniony). | [optional]
**reference_number** | **string** | Numer referencyjny sesji uwierzytelnienia. |
**is_current** | **bool** | Czy sesja jest powiązana z aktualnie używanym tokenem. | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
