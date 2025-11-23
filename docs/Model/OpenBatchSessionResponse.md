# # OpenBatchSessionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**reference_number** | **string** | Numer referencyjny sesji. |
**part_upload_requests** | [**\NetSeven\KseF2Model\PartUploadRequest[]**](PartUploadRequest.md) | Dane wymagane do poprawnego przesłania poszczególnych części pliku paczki faktur.  Każdą część pliku paczki zadeklarowaną w &lt;b&gt;fileParts&lt;/b&gt; należy przesłać zgodnie z odpowiadającym jej obiektem w &lt;b&gt;partUploadRequests&lt;/b&gt;. Łącznikiem pomiędzy deklaracją a instrukcją wysyłki jest pole &lt;b&gt;ordinalNumber&lt;/b&gt;.  Dla każdej części należy: * zastosować metodę HTTP wskazaną w &lt;b&gt;method&lt;/b&gt;, * ustawić adres z &lt;b&gt;url&lt;/b&gt;, * dołączyć nagłówki z &lt;b&gt;headers&lt;/b&gt;, * dołączyć treść części pliku w korpusie żądania.  &#x60;Uwaga: nie należy dodawać do nagłówków token dostępu (accessToken).&#x60;   Każdą część przesyła się oddzielnym żądaniem HTTP.Zwracane kody odpowiedzi:  * &lt;b&gt;201&lt;/b&gt; – poprawne przyjęcie pliku,  * &lt;b&gt;400&lt;/b&gt; – błędne dane,  * &lt;b&gt;401&lt;/b&gt; – nieprawidłowe uwierzytelnienie,  * &lt;b&gt;403&lt;/b&gt; – brak uprawnień do zapisu (np.upłynął czas na zapis). |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
