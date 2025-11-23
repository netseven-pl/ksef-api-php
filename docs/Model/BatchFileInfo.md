# # BatchFileInfo

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**file_size** | **int** | Rozmiar pliku paczki w bajtach. Maksymalny rozmiar paczki to 5GB. |
**file_hash** | **string** | Skrót SHA256 pliku paczki, zakodowany w formacie Base64. |
**file_parts** | [**\NetSeven\KseF2Model\BatchFilePartInfo[]**](BatchFilePartInfo.md) | Informacje o częściach pliku paczki. Maksymalna liczba części to 50. Maksymalny dozwolony rozmiar części przed zaszyfrowaniem to 100MB. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
