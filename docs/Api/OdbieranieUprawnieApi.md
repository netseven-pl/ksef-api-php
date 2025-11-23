# NetSeven\OdbieranieUprawnieApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2PermissionsAuthorizationsGrantsPermissionIdDelete()**](OdbieranieUprawnieApi.md#apiV2PermissionsAuthorizationsGrantsPermissionIdDelete) | **DELETE** /api/v2/permissions/authorizations/grants/{permissionId} | Odebranie uprawnień podmiotowych |
| [**apiV2PermissionsCommonGrantsPermissionIdDelete()**](OdbieranieUprawnieApi.md#apiV2PermissionsCommonGrantsPermissionIdDelete) | **DELETE** /api/v2/permissions/common/grants/{permissionId} | Odebranie uprawnień |


## `apiV2PermissionsAuthorizationsGrantsPermissionIdDelete()`

```php
apiV2PermissionsAuthorizationsGrantsPermissionIdDelete($permission_id): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Odebranie uprawnień podmiotowych

Metoda pozwala na odebranie uprawnienia podmiotowego o wskazanym identyfikatorze.   Wymagane jest wcześniejsze odczytanie uprawnień w celu uzyskania   identyfikatora uprawnienia, które ma zostać odebrane.              > Więcej informacji: > - [Odbieranie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#odebranie-uprawnie%C5%84-podmiotowych)  **Wymagane uprawnienia**: `CredentialsManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\OdbieranieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$permission_id = 'permission_id_example'; // string | Id uprawnienia.

try {
    $result = $apiInstance->apiV2PermissionsAuthorizationsGrantsPermissionIdDelete($permission_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OdbieranieUprawnieApi->apiV2PermissionsAuthorizationsGrantsPermissionIdDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **permission_id** | **string**| Id uprawnienia. | |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsCommonGrantsPermissionIdDelete()`

```php
apiV2PermissionsCommonGrantsPermissionIdDelete($permission_id): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Odebranie uprawnień

Metoda pozwala na odebranie uprawnienia o wskazanym identyfikatorze.   Wymagane jest wcześniejsze odczytanie uprawnień w celu uzyskania   identyfikatora uprawnienia, które ma zostać odebrane.  > Więcej informacji: > - [Odbieranie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#odebranie-uprawnie%C5%84)  **Wymagane uprawnienia**: `CredentialsManage`, `VatUeManage`, `SubunitManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\OdbieranieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$permission_id = 'permission_id_example'; // string | Id uprawnienia.

try {
    $result = $apiInstance->apiV2PermissionsCommonGrantsPermissionIdDelete($permission_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OdbieranieUprawnieApi->apiV2PermissionsCommonGrantsPermissionIdDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **permission_id** | **string**| Id uprawnienia. | |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
