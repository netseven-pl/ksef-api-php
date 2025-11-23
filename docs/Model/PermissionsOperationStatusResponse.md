# # PermissionsOperationStatusResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | [**\NetSeven\KseF2Model\StatusInfo**](StatusInfo.md) | Informacje o aktualnym statusie. | Code | Description | Details | | --- | --- | --- | | 100 | Operacja przyjęta do realizacji | - | | 200 | Operacja zakończona sukcesem | - | | 400 | Operacja zakończona niepowodzeniem | - | | 410 | Podane identyfikatory są niezgodne lub pozostają w niewłaściwej relacji | - | | 420 | Użyte poświadczenia nie mają uprawnień do wykonania tej operacji | - | | 430 | Kontekst identyfikatora nie odpowiada wymaganej roli lub uprawnieniom | - | | 440 | Operacja niedozwolona dla wskazanych powiązań identyfikatorów | - | | 450 | Operacja niedozwolona dla wskazanego identyfikatora lub jego typu | - | | 500 | Nieznany błąd | - | | 550 | Operacja została anulowana przez system | Przetwarzanie zostało przerwane z przyczyn wewnętrznych systemu. Spróbuj ponownie później. | |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
