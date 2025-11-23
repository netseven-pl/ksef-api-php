# NetSeven\UsugiPeppolApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2PeppolQueryGet()**](UsugiPeppolApi.md#apiV2PeppolQueryGet) | **GET** /api/v2/peppol/query | Pobranie listy dostawców usług Peppol |


## `apiV2PeppolQueryGet()`

```php
apiV2PeppolQueryGet($page_offset, $page_size): \NetSeven\KseF2Model\QueryPeppolProvidersResponse
```

Pobranie listy dostawców usług Peppol

Zwraca listę dostawców usług Peppol zarejestrowanych w systemie.  **Sortowanie:**  - dateCreated (Desc)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new NetSeven\Api\UsugiPeppolApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.

try {
    $result = $apiInstance->apiV2PeppolQueryGet($page_offset, $page_size);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsugiPeppolApi->apiV2PeppolQueryGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |

### Return type

[**\NetSeven\KseF2Model\QueryPeppolProvidersResponse**](../Model/QueryPeppolProvidersResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
