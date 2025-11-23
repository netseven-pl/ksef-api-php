# # EncryptionInfo

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**encrypted_symmetric_key** | **string** | Klucz symetryczny o długości 32 bajtów, zaszyfrowany algorytmem RSA (Padding: OAEP z SHA-256), zakodowany w formacie Base64.  [Klucz publiczny Ministersta Finansów](/docs/v2/index.html#tag/Certyfikaty-klucza-publicznego) |
**initialization_vector** | **string** | Wektor inicjalizujący (IV) o długości 16 bajtów, używany do szyfrowania symetrycznego, zakodowany w formacie Base64. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
