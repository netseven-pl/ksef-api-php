# # SendInvoiceRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**invoice_hash** | **string** | Skrót SHA256 oryginalnej faktury, zakodowany w formacie Base64. |
**invoice_size** | **int** | Rozmiar oryginalnej faktury w bajtach. Maksymalny rozmiar zależy od limitów ustawionych dla uwierzytelnionego kontekstu. |
**encrypted_invoice_hash** | **string** | Skrót SHA256 zaszyfrowanej faktury, zakodowany w formacie Base64. |
**encrypted_invoice_size** | **int** | Rozmiar zaszyfrowanej faktury w bajtach. |
**encrypted_invoice_content** | **string** | Faktura zaszyfrowana algorytmem AES-256-CBC z dopełnianiem PKCS#7 (kluczem przekazanym przy otwarciu sesji), zakodowana w formacie Base64. |
**offline_mode** | **bool** | Określa, czy podatnik deklaruje tryb fakturowania \&quot;offline\&quot; dla przesyłanego dokumentu. | [optional] [default to false]
**hash_of_corrected_invoice** | **string** | Skrót SHA256 korygowanej faktury, zakodowany w formacie Base64. Wymagany przy wysyłaniu korekty technicznej faktury. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
