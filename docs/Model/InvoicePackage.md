# # InvoicePackage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**invoice_count** | **int** | Łączna liczba faktur w paczce. |
**size** | **int** | Rozmiar paczki w bajtach. |
**parts** | [**\NetSeven\KseF2Model\InvoicePackagePart[]**](InvoicePackagePart.md) | Lista dostępnych części paczki do pobrania. |
**is_truncated** | **bool** | Określa, czy wynik eksportu został ucięty z powodu przekroczenia limitu liczby faktur lub wielkości paczki. |
**last_issue_date** | **\DateTime** | Data wystawienia ostatniej faktury ujętej w paczce. Pole występuje wyłącznie wtedy, gdy paczka została ucięta i eksport był filtrowany po typie daty &#x60;Issue&#x60;. | [optional]
**last_invoicing_date** | **\DateTime** | Data przyjęcia ostatniej faktury ujętej w paczce. Pole występuje wyłącznie wtedy, gdy paczka została ucięta i eksport był filtrowany po typie daty &#x60;Invoicing&#x60;. | [optional]
**last_permanent_storage_date** | **\DateTime** | Data trwałego zapisu ostatniej faktury ujętej w paczce. Pole występuje wyłącznie wtedy, gdy paczka została ucięta i eksport był filtrowany po typie daty &#x60;PermanentStorage&#x60;. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
