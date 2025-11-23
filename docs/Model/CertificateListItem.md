# # CertificateListItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**certificate_serial_number** | **string** | Numer seryjny certyfikatu (w formacie szesnastkowym). |
**name** | **string** | Nazwa własna certyfikatu. |
**type** | [**\NetSeven\KseF2Model\KsefCertificateType**](KsefCertificateType.md) | Typ certyfikatu. | Wartość | Opis | | --- | --- | | Authentication | Certyfikat używany do uwierzytelnienia w systemie. | | Offline | Certyfikat używany wyłącznie do potwierdzania autentyczności wystawcy i integralności faktury w trybie offline | |
**common_name** | **string** | Nazwa powszechna (CN) podmiotu, dla którego wystawiono certyfikat. |
**status** | [**\NetSeven\KseF2Model\CertificateListItemStatus**](CertificateListItemStatus.md) | Status certyfikatu. | Wartość | Opis | | --- | --- | | Active | Certyfikat jest aktywny i może zostać użyty do uwierzytelnienia lub realizacji operacji w trybie offline (w zależności od typu certyfikatu). | | Blocked | Certyfikat został zablokowany i nie może zostać użyty do uwierzytelnienia i realizacji operacji w trybie offline.            Status przejściowy do czasu zakończenia procesu unieważniania. | | Revoked | Certyfikat został unieważniony i nie może zostać użyty do uwierzytelnienia i realizacji operacji w trybie offline. | | Expired | Certyfikat wygasł i nie może zostać użyty do uwierzytelnienia i realizacji operacji w trybie offline. | |
**subject_identifier** | [**\NetSeven\KseF2Model\CertificateSubjectIdentifier**](CertificateSubjectIdentifier.md) | Identyfikator podmiotu, dla którego wystawiono certyfikat. |
**valid_from** | **\DateTime** | Data rozpoczęcia ważności certyfikatu. |
**valid_to** | **\DateTime** | Data wygaśnięcia certyfikatu. |
**last_use_date** | **\DateTime** | Data ostatniego użycia certyfikatu. | [optional]
**request_date** | **\DateTime** | Data złożenia wniosku certyfikacyjnego. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
