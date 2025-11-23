# NetSeven\OperacjeApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2PermissionsAttachmentsStatusGet()**](OperacjeApi.md#apiV2PermissionsAttachmentsStatusGet) | **GET** /api/v2/permissions/attachments/status | Sprawdzenie statusu zgody na wystawianie faktur z załącznikiem |
| [**apiV2PermissionsOperationsReferenceNumberGet()**](OperacjeApi.md#apiV2PermissionsOperationsReferenceNumberGet) | **GET** /api/v2/permissions/operations/{referenceNumber} | Pobranie statusu operacji |


## `apiV2PermissionsAttachmentsStatusGet()`

```php
apiV2PermissionsAttachmentsStatusGet(): \NetSeven\KseF2Model\CheckAttachmentPermissionStatusResponse
```

Sprawdzenie statusu zgody na wystawianie faktur z załącznikiem

Sprawdzenie czy obecny kontekst posiada zgodę na wystawianie faktur z załącznikiem.  **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\OperacjeApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2PermissionsAttachmentsStatusGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OperacjeApi->apiV2PermissionsAttachmentsStatusGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\CheckAttachmentPermissionStatusResponse**](../Model/CheckAttachmentPermissionStatusResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsOperationsReferenceNumberGet()`

```php
apiV2PermissionsOperationsReferenceNumberGet($reference_number): \NetSeven\KseF2Model\PermissionsOperationStatusResponse
```

Pobranie statusu operacji

Zwraca status operacji asynchronicznej związanej z nadaniem lub odebraniem uprawnień.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\OperacjeApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny operacji nadania lub odbierania uprawnień.

try {
    $result = $apiInstance->apiV2PermissionsOperationsReferenceNumberGet($reference_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OperacjeApi->apiV2PermissionsOperationsReferenceNumberGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny operacji nadania lub odbierania uprawnień. | |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationStatusResponse**](../Model/PermissionsOperationStatusResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
