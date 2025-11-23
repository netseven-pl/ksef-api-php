# # SessionsQueryResponseItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**reference_number** | **string** | Numer referencyjny sesji. |
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Status sesji. |
**date_created** | **\DateTime** | Data utworzenia sesji. |
**date_updated** | **\DateTime** | Data ostatniej aktywności w ramach sesji. |
**valid_until** | **\DateTime** | Termin ważności sesji. Po jego upływie sesja interaktywna zostanie automatycznie zamknięta. | [optional]
**total_invoice_count** | **int** | Łączna liczba faktur (uwzględnia również te w trakcie przetwarzania). |
**successful_invoice_count** | **int** | Liczba poprawnie przetworzonych faktur. |
**failed_invoice_count** | **int** | Liczba błędnie przetworzonych faktur. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
