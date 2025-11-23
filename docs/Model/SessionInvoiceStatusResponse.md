# # SessionInvoiceStatusResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ordinal_number** | **int** | Numer sekwencyjny faktury w ramach sesji. |
**invoice_number** | **string** | Numer faktury. | [optional]
**ksef_number** | **string** | Numer KSeF. | [optional]
**reference_number** | **string** | Numer referencyjny faktury. |
**invoice_hash** | **string** | Skrót SHA256 faktury, zakodowany w formacie Base64. |
**invoice_file_name** | **string** | Nazwa pliku faktury (zwracana dla faktur wysyłanych wsadowo). | [optional]
**acquisition_date** | **\DateTime** | Data nadania numeru KSeF. | [optional]
**invoicing_date** | **\DateTime** | Data przyjęcia faktury w systemie KSeF (do dalszego przetwarzania). |
**permanent_storage_date** | **\DateTime** | Data trwałego zapisu faktury w repozytorium KSeF. Wartość uzupełniana asynchronicznie w momencie trwałego zapisu; zawsze późniejsza niż &lt;b&gt;acquisitionDate&lt;/b&gt;. Podczas sprawdzania statusu może być jeszcze niedostępna. | [optional]
**upo_download_url** | **string** | Adres do pobrania UPO. Link generowany jest przy każdym odpytaniu o status.  Dostęp odbywa się metodą &#x60;HTTP GET&#x60; i &lt;b&gt;nie należy&lt;/b&gt; wysyłać tokenu dostępowego.  Link nie podlega limitom API i wygasa po określonym czasie w &#x60;UpoDownloadUrlExpirationDate&#x60;. | [optional]
**upo_download_url_expiration_date** | **\DateTime** | Data i godzina wygaśnięcia adresu. Po tej dacie link &#x60;UpoDownloadUrl&#x60; nie będzie już aktywny. | [optional]
**invoicing_mode** | [**\NetSeven\KseF2Model\InvoicingMode**](InvoicingMode.md) | Tryb fakturowania (online/offline). | [optional]
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Status faktury.  | Code | Description | Details | | --- | --- | --- | | 100 | Faktura przyjęta do dalszego przetwarzania | - | | 150 | Trwa przetwarzanie | - | | 200 | Sukces | - | | 405 | Przetwarzanie anulowane z powodu błędu sesji | - | | 410 | Nieprawidłowy zakres uprawnień | - | | 415 | Brak możliwości wysyłania faktury z załącznikiem | - | | 430 | Błąd weryfikacji pliku faktury | - | | 435 | Błąd odszyfrowania pliku | - | | 440 | Duplikat faktury | - | | 450 | Błąd weryfikacji semantyki dokumentu faktury | - | | 500 | Nieznany błąd ({statusCode}) | - | | 550 | Operacja została anulowana przez system | Przetwarzanie zostało przerwane z przyczyn wewnętrznych systemu. Spróbuj ponownie | |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
