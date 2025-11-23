# # InvoiceQueryDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date_type** | [**\NetSeven\KseF2Model\InvoiceQueryDateType**](InvoiceQueryDateType.md) | Typ daty, według której ma być zastosowany zakres. | Wartość | Opis | | --- | --- | | Issue | Data wystawienia faktury. | | Invoicing | Data przyjęcia faktury w systemie KSeF (do dalszego przetwarzania). | | PermanentStorage | Data trwałego zapisu faktury w repozytorium systemu KSeF. | |
**from** | **\DateTime** | Data początkowa zakresu(UTC). |
**to** | **\DateTime** | Data końcowa zakresu(UTC). Jeśli nie zostanie podana, przyjmowana jest bieżąca data i czas w UTC. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
