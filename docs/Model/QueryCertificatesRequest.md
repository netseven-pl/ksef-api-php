# # QueryCertificatesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**certificate_serial_number** | **string** | Numer seryjny certyfikatu. Wyszukiwanie odbywa się na zasadzie dokładnego dopasowania (exact match). | [optional]
**name** | **string** | Nazwa własna certyfikatu. Wyszukiwanie jest częściowe, czyli zwracane są certyfikaty, których nazwa zawiera podany ciąg znaków (contains). | [optional]
**type** | [**\NetSeven\KseF2Model\KsefCertificateType**](KsefCertificateType.md) | Typ certyfikatu KSeF. | Wartość | Opis | | --- | --- | | Authentication | Certyfikat używany do uwierzytelnienia w systemie. | | Offline | Certyfikat używany wyłącznie do potwierdzania autentyczności wystawcy i integralności faktury w trybie offline | | [optional]
**status** | [**\NetSeven\KseF2Model\CertificateListItemStatus**](CertificateListItemStatus.md) | Status certyfikatu. | Wartość | Opis | | --- | --- | | Active | Certyfikat jest aktywny i może zostać użyty do uwierzytelnienia lub realizacji operacji w trybie offline (w zależności od typu certyfikatu). | | Blocked | Certyfikat został zablokowany i nie może zostać użyty do uwierzytelnienia i realizacji operacji w trybie offline.            Status przejściowy do czasu zakończenia procesu unieważniania. | | Revoked | Certyfikat został unieważniony i nie może zostać użyty do uwierzytelnienia i realizacji operacji w trybie offline. | | Expired | Certyfikat wygasł i nie może zostać użyty do uwierzytelnienia i realizacji operacji w trybie offline. | | [optional]
**expires_after** | **\DateTime** | Filtruje certyfikaty, które wygasają po podanej dacie. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
