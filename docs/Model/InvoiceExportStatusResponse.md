# # InvoiceExportStatusResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Status eksportu.  | Code | Description | Details | | --- | --- | --- | | 100 | Eksport faktur w toku | - | | 200 | Eksport faktur zakończony sukcesem | - | | 210 | Eksport faktur wygasł i nie jest już dostępny do pobrania | - | | 415 | Błąd odszyfrowania dostarczonego klucza  | - | | 500 | Nieznany błąd ({statusCode}) | - | | 550 | Operacja została anulowana przez system | Przetwarzanie zostało przerwane z przyczyn wewnętrznych systemu. Spróbuj ponownie | |
**completed_date** | **\DateTime** | Data zakończenia przetwarzania żądania eksportu faktur. | [optional]
**package_expiration_date** | **\DateTime** | Data wygaśnięcia paczki faktur przygotowanej do pobrania. Po upływie tej daty paczka nie będzie już dostępna do pobrania. | [optional]
**package** | [**\NetSeven\KseF2Model\InvoicePackage**](InvoicePackage.md) | Dane paczki faktur przygotowanej do pobrania. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
