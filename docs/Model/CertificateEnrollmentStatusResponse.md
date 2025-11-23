# # CertificateEnrollmentStatusResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**request_date** | **\DateTime** | Data złożenia wniosku certyfikacyjnego. |
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Informacje o aktualnym statusie. | Code | Description | Details | | --- | --- | --- | | 100 | Wniosek przyjęty do realizacji | - | | 200 | Wniosek obsłużony (certyfikat wygenerowany) | - | | 400 | Wniosek odrzucony | Klucz publiczny został już certyfikowany przez inny podmiot. | | 400 | Wniosek odrzucony | Osiągnięto dopuszczalny limit posiadanych certyfikatów. | | 500 | Nieznany błąd | - | | 550 | Operacja została anulowana przez system | Przetwarzanie zostało przerwane z przyczyn wewnętrznych systemu. Spróbuj ponownie | |
**certificate_serial_number** | **string** | Numer seryjny wygenerowanego certyfikatu (w formacie szesnastkowym).  Zwracany w przypadku prawidłowego przeprocesowania wniosku certyfikacyjnego. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
