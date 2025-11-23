# # SessionStatusResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Informacje o aktualnym statusie.              Sesja wsadowa: | Code | Description | Details | | --- | --- | --- | | 100 | Sesja wsadowa rozpoczęta | - | | 150 | Trwa przetwarzanie | - | | 200 | Sesja wsadowa przetworzona pomyślnie | - | | 405 | Błąd weryfikacji poprawności dostarczonych elementów paczki | - | | 415 | Błąd odszyfrowania dostarczonego klucza | - | | 420 | Przekroczony limit faktur w sesji | - | | 430 | Błąd dekompresji pierwotnego archiwum | - | | 435 | Błąd odszyfrowania zaszyfrowanych części archiwum | - | | 440 | Sesja anulowana | Przekroczono czas wysyłki | | 440 | Sesja anulowana | Nie przesłano faktur | | 445 | Błąd weryfikacji, brak poprawnych faktur | - | | 500 | Nieznany błąd ({statusCode}) | - |  Sesja interaktywna: | Code | Description | Details | | --- | --- | --- | | 100 | Sesja interaktywna otwarta | - | | 170 | Sesja interaktywna zamknięta | - | | 200 | Sesja interaktywna przetworzona pomyślnie | - | | 415 | Błąd odszyfrowania dostarczonego klucza | - | | 440 | Sesja anulowana | Nie przesłano faktur | | 445 | Błąd weryfikacji, brak poprawnych faktur | - | | * | description missing | - | |
**valid_until** | **\DateTime** | Termin ważności sesji. Po jego upływie sesja zostanie automatycznie zamknięta. | [optional] [readonly]
**upo** | [**\NetSeven\KseF2Model\UpoResponse**](UpoResponse.md) | Informacja o UPO sesyjnym, zwracana gdy sesja została zamknięta i UPO zostało wygenerowane. | [optional]
**invoice_count** | **int** | Liczba przyjętych faktur w ramach sesji. | [optional]
**successful_invoice_count** | **int** | Liczba faktur przeprocesowanych w ramach sesji z sukcesem . | [optional]
**failed_invoice_count** | **int** | Liczba faktur przeprocesowanych w ramach sesji z błędem. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
