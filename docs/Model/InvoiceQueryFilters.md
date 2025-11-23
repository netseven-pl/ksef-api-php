# # InvoiceQueryFilters

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subject_type** | [**\NetSeven\KseF2Model\InvoiceQuerySubjectType**](InvoiceQuerySubjectType.md) | Typ podmiotu, którego dotyczą kryteria filtrowania metadanych faktur. Określa kontekst, w jakim przeszukiwane są dane. | Wartość | Opis | | --- | --- | | Subject1 | Podmiot 1 - sprzedawca | | Subject2 | Podmiot 2 - nabywca | | Subject3 | Podmiot 3 | | SubjectAuthorized | Podmiot upoważniony | |
**date_range** | [**\NetSeven\KseF2Model\InvoiceQueryDateRange**](InvoiceQueryDateRange.md) | Typ i zakres dat, według którego mają być filtrowane faktury. Dozwolony maksymalny okres wynosi 2 lata. |
**ksef_number** | **string** | Numer KSeF faktury (exact match). | [optional]
**invoice_number** | **string** | Numer faktury nadany przez wystawcę (exact match). | [optional]
**amount** | [**\NetSeven\KseF2Model\InvoiceQueryAmount**](InvoiceQueryAmount.md) | Filtr kwotowy – brutto, netto lub VAT (z wartością). | [optional]
**seller_nip** | **string** | Nip sprzedawcy (exact match). | [optional]
**buyer_identifier** | [**\NetSeven\KseF2Model\InvoiceQueryBuyerIdentifier**](InvoiceQueryBuyerIdentifier.md) | Identyfikator nabywcy. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | VatUe | Identyfikator VAT UE podmiotu unijnego. | | Other | Inny identyfikator| | None  | Brak identyfikatora nabywcy | | [optional]
**currency_codes** | [**\NetSeven\KseF2Model\CurrencyCode[]**](CurrencyCode.md) | Kody walut. | [optional]
**invoicing_mode** | [**\NetSeven\KseF2Model\InvoicingMode**](InvoicingMode.md) | Tryb wystawienia faktury: online lub offline. | [optional]
**is_self_invoicing** | **bool** | Czy faktura została wystawiona w trybie samofakturowania. | [optional]
**form_type** | [**\NetSeven\KseF2Model\InvoiceQueryFormType**](InvoiceQueryFormType.md) | Typ dokumentu. | Wartość | Opis | | --- | --- | | FA | Faktura VAT | | PEF | Faktura PEF | | RR | Faktura RR | | [optional]
**invoice_types** | [**\NetSeven\KseF2Model\InvoiceType[]**](InvoiceType.md) | Rodzaje faktur. | Wartość | Opis | | --- | --- | | Vat | (FA) Podstawowa | | Zal | (FA) Zaliczkowa | | Kor | (FA) Korygująca | | Roz | (FA) Rozliczeniowa | | Upr | (FA) Uproszczona | | KorZal | (FA) Korygująca fakturę zaliczkową | | KorRoz | (FA) Korygująca fakturę rozliczeniową | | VatPef | (PEF) Podstawowowa | | VatPefSp | (PEF) Specjalizowana | | KorPef | (PEF) Korygująca | | VatRr | (RR) Podstawowa | | KorVatRr | (RR) Korygująca | | [optional]
**has_attachment** | **bool** | Czy faktura ma załącznik. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
