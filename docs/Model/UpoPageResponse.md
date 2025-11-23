# # UpoPageResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**reference_number** | **string** | Numer referencyjny strony UPO. |
**download_url** | **string** | Adres do pobrania strony UPO. Link generowany jest przy każdym odpytaniu o status.  Dostęp odbywa się metodą &#x60;HTTP GET&#x60; i &lt;b&gt;nie należy&lt;/b&gt; wysyłać tokenu dostępowego.  Link nie podlega limitom API i wygasa po określonym czasie w &#x60;DownloadUrlExpirationDate&#x60;. |
**download_url_expiration_date** | **\DateTime** | Data i godzina wygaśnięcia adresu. Po tej dacie link &#x60;DownloadUrl&#x60; nie będzie już aktywny. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
