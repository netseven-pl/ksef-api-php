# # EnrollCertificateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**certificate_name** | **string** | Nazwa własna certyfikatu. |
**certificate_type** | [**\NetSeven\KseF2Model\KsefCertificateType**](KsefCertificateType.md) | Typ certyfikatu. | Wartość | Opis | | --- | --- | | Authentication | Certyfikat używany do uwierzytelnienia w systemie. | | Offline | Certyfikat używany wyłącznie do potwierdzania autentyczności wystawcy i integralności faktury w trybie offline | |
**csr** | **string** | Wniosek certyfikacyjny PKCS#10 (CSR) w formacie DER zakodowany w Base64. |
**valid_from** | **\DateTime** | Data rozpoczęcia ważności certyfikatu. Jeśli nie zostanie podana, certyfikat będzie ważny od momentu jego wystawienia. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
