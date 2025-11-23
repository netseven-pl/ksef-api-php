# NetSeven\AktywneSesjeApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2AuthSessionsCurrentDelete()**](AktywneSesjeApi.md#apiV2AuthSessionsCurrentDelete) | **DELETE** /api/v2/auth/sessions/current | Unieważnienie aktualnej sesji uwierzytelnienia |
| [**apiV2AuthSessionsGet()**](AktywneSesjeApi.md#apiV2AuthSessionsGet) | **GET** /api/v2/auth/sessions | Pobranie listy aktywnych sesji |
| [**apiV2AuthSessionsReferenceNumberDelete()**](AktywneSesjeApi.md#apiV2AuthSessionsReferenceNumberDelete) | **DELETE** /api/v2/auth/sessions/{referenceNumber} | Unieważnienie sesji uwierzytelnienia |


## `apiV2AuthSessionsCurrentDelete()`

```php
apiV2AuthSessionsCurrentDelete()
```

Unieważnienie aktualnej sesji uwierzytelnienia

Unieważnia sesję powiązaną z tokenem użytym do wywołania tej operacji.  Unieważnienie sesji sprawia, że powiązany z nią refresh token przestaje działać i nie można już za jego pomocą uzyskać kolejnych access tokenów. **Aktywne access tokeny działają do czasu minięcia ich termin ważności.**  Sposób uwierzytelnienia: `RefreshToken` lub `AccessToken`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\AktywneSesjeApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $apiInstance->apiV2AuthSessionsCurrentDelete();
} catch (Exception $e) {
    echo 'Exception when calling AktywneSesjeApi->apiV2AuthSessionsCurrentDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthSessionsGet()`

```php
apiV2AuthSessionsGet($x_continuation_token, $page_size): \NetSeven\KseF2Model\AuthenticationListResponse
```

Pobranie listy aktywnych sesji

Zwraca listę aktywnych sesji uwierzytelnienia.  **Sortowanie:**  - startDate (Desc)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\AktywneSesjeApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$x_continuation_token = 'x_continuation_token_example'; // string | Token służący do pobrania kolejnej strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.

try {
    $result = $apiInstance->apiV2AuthSessionsGet($x_continuation_token, $page_size);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AktywneSesjeApi->apiV2AuthSessionsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **x_continuation_token** | **string**| Token służący do pobrania kolejnej strony wyników. | [optional] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |

### Return type

[**\NetSeven\KseF2Model\AuthenticationListResponse**](../Model/AuthenticationListResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthSessionsReferenceNumberDelete()`

```php
apiV2AuthSessionsReferenceNumberDelete($reference_number)
```

Unieważnienie sesji uwierzytelnienia

Unieważnia sesję o podanym numerze referencyjnym.  Unieważnienie sesji sprawia, że powiązany z nią refresh token przestaje działać i nie można już za jego pomocą uzyskać kolejnych access tokenów. **Aktywne access tokeny działają do czasu minięcia ich termin ważności.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\AktywneSesjeApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny sesji uwierzytelnienia.

try {
    $apiInstance->apiV2AuthSessionsReferenceNumberDelete($reference_number);
} catch (Exception $e) {
    echo 'Exception when calling AktywneSesjeApi->apiV2AuthSessionsReferenceNumberDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny sesji uwierzytelnienia. | |

### Return type

void (empty response body)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
