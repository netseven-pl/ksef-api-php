# # OpenBatchSessionRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**form_code** | [**\NetSeven\KseF2Model\FormCode**](FormCode.md) | Schemat faktur wysyłanych w ramach sesji.  Obsługiwane schematy: | SystemCode | SchemaVersion | Value | | --- | --- | --- | | FA (2) | 1-0E | FA | | FA (3) | 1-0E | FA | |
**batch_file** | [**\NetSeven\KseF2Model\BatchFileInfo**](BatchFileInfo.md) | Informacje o przesyłanej paczce faktur. |
**encryption** | [**\NetSeven\KseF2Model\EncryptionInfo**](EncryptionInfo.md) | Symetryczny klucz szyfrujący plik paczki, zaszyfrowany kluczem publicznym Ministerstwa Finansów. |
**offline_mode** | **bool** | Określa, czy podatnik deklaruje tryb fakurowania \&quot;offline\&quot; dla dokumentów przesyłanych w sesji wsadowej. | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
