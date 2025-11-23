# # InvoiceMetadata

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ksef_number** | **string** | Numer KSeF faktury. |
**invoice_number** | **string** | Numer faktury nadany przez wystawcę. |
**issue_date** | **\DateTime** | Data wystawienia faktury. |
**invoicing_date** | **\DateTime** | Data przyjęcia faktury w systemie KSeF (do dalszego przetwarzania). |
**acquisition_date** | **\DateTime** | Data nadania numeru KSeF. |
**permanent_storage_date** | **\DateTime** | Data trwałego zapisu faktury w repozytorium systemu KSeF. |
**seller** | [**\NetSeven\KseF2Model\InvoiceMetadataSeller**](InvoiceMetadataSeller.md) | Dane identyfikujące sprzedawcę. |
**buyer** | [**\NetSeven\KseF2Model\InvoiceMetadataBuyer**](InvoiceMetadataBuyer.md) | Dane identyfikujące nabywcę. |
**net_amount** | **float** | Łączna kwota netto. |
**gross_amount** | **float** | Łączna kwota brutto. |
**vat_amount** | **float** | Łączna kwota VAT. |
**currency** | **string** | Kod waluty. |
**invoicing_mode** | [**\NetSeven\KseF2Model\InvoicingMode**](InvoicingMode.md) | Tryb fakturowania (online/offline). |
**invoice_type** | [**\NetSeven\KseF2Model\InvoiceType**](InvoiceType.md) | Rodzaj faktury. | Wartość | Opis | | --- | --- | | Vat | (FA) Podstawowa | | Zal | (FA) Zaliczkowa | | Kor | (FA) Korygująca | | Roz | (FA) Rozliczeniowa | | Upr | (FA) Uproszczona | | KorZal | (FA) Korygująca fakturę zaliczkową | | KorRoz | (FA) Korygująca fakturę rozliczeniową | | VatPef | (PEF) Podstawowowa | | VatPefSp | (PEF) Specjalizowana | | KorPef | (PEF) Korygująca | | VatRr | (RR) Podstawowa | | KorVatRr | (RR) Korygująca | |
**form_code** | [**\NetSeven\KseF2Model\FormCode**](FormCode.md) | Struktura dokumentu faktury.  Obsługiwane schematy: | SystemCode | SchemaVersion | Value | | --- | --- | --- | | FA (2) | 1-0E | FA | | FA (3) | 1-0E | FA | | PEF (3) | 2-1 | PEF | | PEF_KOR (3) | 2-1 | PEF | |
**is_self_invoicing** | **bool** | Czy faktura została wystawiona w trybie samofakturowania. |
**has_attachment** | **bool** | Określa, czy faktura posiada załącznik. |
**invoice_hash** | **string** | Skrót SHA256 faktury. |
**hash_of_corrected_invoice** | **string** | Skrót SHA256 korygowanej faktury. | [optional]
**third_subjects** | [**\NetSeven\KseF2Model\InvoiceMetadataThirdSubject[]**](InvoiceMetadataThirdSubject.md) | Lista podmiotów trzecich. | [optional]
**authorized_subject** | [**\NetSeven\KseF2Model\InvoiceMetadataAuthorizedSubject**](InvoiceMetadataAuthorizedSubject.md) | Podmiot upoważniony. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
