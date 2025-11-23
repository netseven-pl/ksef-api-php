# NetSeven\LimityIOgraniczeniaApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2LimitsContextGet()**](LimityIOgraniczeniaApi.md#apiV2LimitsContextGet) | **GET** /api/v2/limits/context | Pobranie limitów dla bieżącego kontekstu |
| [**apiV2LimitsSubjectGet()**](LimityIOgraniczeniaApi.md#apiV2LimitsSubjectGet) | **GET** /api/v2/limits/subject | Pobranie limitów dla bieżącego podmiotu |
| [**apiV2RateLimitsGet()**](LimityIOgraniczeniaApi.md#apiV2RateLimitsGet) | **GET** /api/v2/rate-limits | Pobranie aktualnie obowiązujących limitów API |
| [**apiV2TestdataLimitsContextSessionDelete()**](LimityIOgraniczeniaApi.md#apiV2TestdataLimitsContextSessionDelete) | **DELETE** /api/v2/testdata/limits/context/session | Przywrócenie domyślnych wartości limitów sesji dla bieżącego kontekstu |
| [**apiV2TestdataLimitsContextSessionPost()**](LimityIOgraniczeniaApi.md#apiV2TestdataLimitsContextSessionPost) | **POST** /api/v2/testdata/limits/context/session | Zmiana limitów sesji dla bieżącego kontekstu |
| [**apiV2TestdataLimitsSubjectCertificateDelete()**](LimityIOgraniczeniaApi.md#apiV2TestdataLimitsSubjectCertificateDelete) | **DELETE** /api/v2/testdata/limits/subject/certificate | Przywrócenie domyślnych wartości limitów certyfikatów dla bieżącego podmiotu |
| [**apiV2TestdataLimitsSubjectCertificatePost()**](LimityIOgraniczeniaApi.md#apiV2TestdataLimitsSubjectCertificatePost) | **POST** /api/v2/testdata/limits/subject/certificate | Zmiana limitów certyfikatów dla bieżącego podmiotu |
| [**apiV2TestdataRateLimitsDelete()**](LimityIOgraniczeniaApi.md#apiV2TestdataRateLimitsDelete) | **DELETE** /api/v2/testdata/rate-limits | Przywrócenie domyślnych wartości limitów API dla bieżącego kontekstu |
| [**apiV2TestdataRateLimitsPost()**](LimityIOgraniczeniaApi.md#apiV2TestdataRateLimitsPost) | **POST** /api/v2/testdata/rate-limits | Zmiana limitów API dla bieżącego kontekstu |


## `apiV2LimitsContextGet()`

```php
apiV2LimitsContextGet(): \NetSeven\KseF2Model\EffectiveContextLimits
```

Pobranie limitów dla bieżącego kontekstu

Zwraca wartości aktualnie obowiązujących limitów dla bieżącego kontekstu.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2LimitsContextGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2LimitsContextGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\EffectiveContextLimits**](../Model/EffectiveContextLimits.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2LimitsSubjectGet()`

```php
apiV2LimitsSubjectGet(): \NetSeven\KseF2Model\EffectiveSubjectLimits
```

Pobranie limitów dla bieżącego podmiotu

Zwraca wartoście aktualnie obowiązujących limitów dla bieżącego podmiotu.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2LimitsSubjectGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2LimitsSubjectGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\EffectiveSubjectLimits**](../Model/EffectiveSubjectLimits.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2RateLimitsGet()`

```php
apiV2RateLimitsGet(): \NetSeven\KseF2Model\EffectiveApiRateLimits
```

Pobranie aktualnie obowiązujących limitów API

Zwraca wartości aktualnie obowiązujących limitów ilości żądań przesyłanych do API.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2RateLimitsGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2RateLimitsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\EffectiveApiRateLimits**](../Model/EffectiveApiRateLimits.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2TestdataLimitsContextSessionDelete()`

```php
apiV2TestdataLimitsContextSessionDelete()
```

Przywrócenie domyślnych wartości limitów sesji dla bieżącego kontekstu

Przywraca wartości aktualnie obowiązujących limitów sesji dla bieżącego kontekstu do wartości domyślnych. **Tylko na środowiskach testowych.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $apiInstance->apiV2TestdataLimitsContextSessionDelete();
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2TestdataLimitsContextSessionDelete: ', $e->getMessage(), PHP_EOL;
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

## `apiV2TestdataLimitsContextSessionPost()`

```php
apiV2TestdataLimitsContextSessionPost($set_session_limits_request)
```

Zmiana limitów sesji dla bieżącego kontekstu

Zmienia wartości aktualnie obowiązujących limitów sesji dla bieżącego kontekstu. **Tylko na środowiskach testowych.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$set_session_limits_request = new \NetSeven\KseF2Model\SetSessionLimitsRequest(); // \NetSeven\KseF2Model\SetSessionLimitsRequest

try {
    $apiInstance->apiV2TestdataLimitsContextSessionPost($set_session_limits_request);
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2TestdataLimitsContextSessionPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **set_session_limits_request** | [**\NetSeven\KseF2Model\SetSessionLimitsRequest**](../Model/SetSessionLimitsRequest.md)|  | [optional] |

### Return type

void (empty response body)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2TestdataLimitsSubjectCertificateDelete()`

```php
apiV2TestdataLimitsSubjectCertificateDelete()
```

Przywrócenie domyślnych wartości limitów certyfikatów dla bieżącego podmiotu

Przywraca wartości aktualnie obowiązujących limitów certyfikatów dla bieżącego podmiotu do wartości domyślnych. **Tylko na środowiskach testowych.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $apiInstance->apiV2TestdataLimitsSubjectCertificateDelete();
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2TestdataLimitsSubjectCertificateDelete: ', $e->getMessage(), PHP_EOL;
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

## `apiV2TestdataLimitsSubjectCertificatePost()`

```php
apiV2TestdataLimitsSubjectCertificatePost($set_subject_limits_request)
```

Zmiana limitów certyfikatów dla bieżącego podmiotu

Zmienia wartości aktualnie obowiązujących limitów certyfikatów dla bieżącego podmiotu. **Tylko na środowiskach testowych.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$set_subject_limits_request = new \NetSeven\KseF2Model\SetSubjectLimitsRequest(); // \NetSeven\KseF2Model\SetSubjectLimitsRequest

try {
    $apiInstance->apiV2TestdataLimitsSubjectCertificatePost($set_subject_limits_request);
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2TestdataLimitsSubjectCertificatePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **set_subject_limits_request** | [**\NetSeven\KseF2Model\SetSubjectLimitsRequest**](../Model/SetSubjectLimitsRequest.md)|  | [optional] |

### Return type

void (empty response body)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2TestdataRateLimitsDelete()`

```php
apiV2TestdataRateLimitsDelete()
```

Przywrócenie domyślnych wartości limitów API dla bieżącego kontekstu

Przywraca wartości aktualnie obowiązujących limitów żądań przesyłąnych do API dla bieżącego kontekstu do wartości domyślnych. **Tylko na środowiskach testowych.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $apiInstance->apiV2TestdataRateLimitsDelete();
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2TestdataRateLimitsDelete: ', $e->getMessage(), PHP_EOL;
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

## `apiV2TestdataRateLimitsPost()`

```php
apiV2TestdataRateLimitsPost($set_rate_limits_request)
```

Zmiana limitów API dla bieżącego kontekstu

Zmienia wartości aktualnie obowiązujących limitów żądań przesyłąnych do API dla bieżącego kontekstu. **Tylko na środowiskach testowych.**

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\LimityIOgraniczeniaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$set_rate_limits_request = new \NetSeven\KseF2Model\SetRateLimitsRequest(); // \NetSeven\KseF2Model\SetRateLimitsRequest

try {
    $apiInstance->apiV2TestdataRateLimitsPost($set_rate_limits_request);
} catch (Exception $e) {
    echo 'Exception when calling LimityIOgraniczeniaApi->apiV2TestdataRateLimitsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **set_rate_limits_request** | [**\NetSeven\KseF2Model\SetRateLimitsRequest**](../Model/SetRateLimitsRequest.md)|  | [optional] |

### Return type

void (empty response body)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
