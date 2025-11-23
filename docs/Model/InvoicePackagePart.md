# # InvoicePackagePart

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ordinal_number** | **int** | Numer sekwencyjny pliku części paczki. |
**part_name** | **string** | Nazwa pliku części paczki. |
**method** | **string** | Metoda HTTP, której należy użyć przy pobieraniu pliku. |
**url** | **string** | Adres URL, pod który należy wysłać żądanie pobrania części paczki. Link jest generowany dynamicznie w momencie odpytania o status operacji eksportu. Nie podlega limitom API i nie wymaga przesyłania tokenu dostępowego przy pobraniu. |
**part_size** | **int** | Rozmiar części paczki w bajtach. |
**part_hash** | **string** | Skrót SHA256 pliku części paczki, zakodowany w formacie Base64. |
**encrypted_part_size** | **int** | Rozmiar zaszyfrowanej części paczki w bajtach. |
**encrypted_part_hash** | **string** | Skrót SHA256 zaszyfrowanej części paczki, zakodowany w formacie Base64. |
**expiration_date** | **\DateTime** | Data i godzina wygaśnięcia linku umożliwiającego pobranie części paczki. Po upływie tego momentu link przestaje być aktywny. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
