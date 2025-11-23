# NetSeven\WysykaInteraktywnaApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2SessionsOnlinePost()**](WysykaInteraktywnaApi.md#apiV2SessionsOnlinePost) | **POST** /api/v2/sessions/online | Otwarcie sesji interaktywnej |
| [**apiV2SessionsOnlineReferenceNumberClosePost()**](WysykaInteraktywnaApi.md#apiV2SessionsOnlineReferenceNumberClosePost) | **POST** /api/v2/sessions/online/{referenceNumber}/close | Zamknięcie sesji interaktywnej |
| [**apiV2SessionsOnlineReferenceNumberInvoicesPost()**](WysykaInteraktywnaApi.md#apiV2SessionsOnlineReferenceNumberInvoicesPost) | **POST** /api/v2/sessions/online/{referenceNumber}/invoices | Wysłanie faktury |


## `apiV2SessionsOnlinePost()`

```php
apiV2SessionsOnlinePost($open_online_session_request): \NetSeven\KseF2Model\OpenOnlineSessionResponse
```

Otwarcie sesji interaktywnej

Otwiera sesję do wysyłki pojedynczych faktur. Należy przekazać schemat wysyłanych faktur oraz informacje o kluczu używanym do szyfrowania.  > Więcej informacji: > - [Otwarcie sesji interaktywnej](https://github.com/CIRFMF/ksef-docs/blob/main/sesja-interaktywna.md#1-otwarcie-sesji) > - [Klucz publiczny Ministersta Finansów](/docs/v2/index.html#tag/Certyfikaty-klucza-publicznego)  **Wymagane uprawnienia**: `InvoiceWrite`, `PefInvoiceWrite`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WysykaInteraktywnaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$open_online_session_request = {"formCode":{"systemCode":"FA (3)","schemaVersion":"1-0E","value":"FA"},"encryption":{"encryptedSymmetricKey":"bdUVjqLj+y2q6aBUuLxxXYAMqeDuIBRTyr+hB96DaWKaGzuVHw9p+Nk9vhzgF/Q5cavK2k6eCh6SdsrWI0s9mFFj4A4UJtsyD8Dn3esLfUZ5A1juuG3q3SBi/XOC/+9W+0T/KdwdE393mbiUNyx1K/0bw31vKJL0COeJIDP7usAMDl42/H1TNvkjk+8iZ80V0qW7D+RZdz+tdiY1xV0f2mfgwJ46V0CpZ+sB9UAssRj+eVffavJ0TOg2b5JaBxE8MCAvrF6rO5K4KBjUmoy7PP7g1qIbm8xI2GO0KnfPOO5OWj8rsotRwBgu7x19Ine3qYUvuvCZlXRGGZ5NHIzWPM4O74+gNalaMgFCsmv8mMhETSU4SfAGmJr9edxPjQSbgD5i2X4eDRDMwvyaAa7CP1b2oICju+0L7Fywd2ZtUcr6El++eTVoi8HYsTArntET++gULT7XXjmb8e3O0nxrYiYsE9GMJ7HBGv3NOoJ1NTm3a7U6+c0ZJiBVLvn6xXw10LQX243xH+ehsKo6djQJKYtqcNPaXtCwM1c9RrsOx/wRXyWCtTffqLiaR0LbYvfMJAcEWceG+RaeAx4p37OiQqdJypd6LAv9/0ECWK8Bip8yyoA+0EYiAJb9YuDz2YlQX9Mx9E9FzFIAsgEQ2w723HZYWgPywLb+dlsum4lTZKQ=","initializationVector":"OmtDQdl6vkOI1GLKZSjgEg=="}}; // \NetSeven\KseF2Model\OpenOnlineSessionRequest

try {
    $result = $apiInstance->apiV2SessionsOnlinePost($open_online_session_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WysykaInteraktywnaApi->apiV2SessionsOnlinePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **open_online_session_request** | [**\NetSeven\KseF2Model\OpenOnlineSessionRequest**](../Model/OpenOnlineSessionRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\OpenOnlineSessionResponse**](../Model/OpenOnlineSessionResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2SessionsOnlineReferenceNumberClosePost()`

```php
apiV2SessionsOnlineReferenceNumberClosePost($reference_number)
```

Zamknięcie sesji interaktywnej

Zamyka sesję interaktywną i rozpoczyna generowanie zbiorczego UPO dla sesji.  **Wymagane uprawnienia**: `InvoiceWrite`, `PefInvoiceWrite`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WysykaInteraktywnaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny sesji

try {
    $apiInstance->apiV2SessionsOnlineReferenceNumberClosePost($reference_number);
} catch (Exception $e) {
    echo 'Exception when calling WysykaInteraktywnaApi->apiV2SessionsOnlineReferenceNumberClosePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny sesji | |

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

## `apiV2SessionsOnlineReferenceNumberInvoicesPost()`

```php
apiV2SessionsOnlineReferenceNumberInvoicesPost($reference_number, $send_invoice_request): \NetSeven\KseF2Model\SendInvoiceResponse
```

Wysłanie faktury

Przyjmuje zaszyfrowaną fakturę oraz jej metadane i rozpoczyna jej przetwarzanie.  > Więcej informacji: > - [Wysłanie faktury](https://github.com/CIRFMF/ksef-docs/blob/main/sesja-interaktywna.md#2-wys%C5%82anie-faktury)  **Wymagane uprawnienia**: `InvoiceWrite`, `PefInvoiceWrite`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WysykaInteraktywnaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny sesji
$send_invoice_request = {"invoiceHash":"EbrK4cOSjW4hEpJaHU71YXSOZZmqP5++dK9nLgTzgV4=","invoiceSize":6480,"encryptedInvoiceHash":"miYb1z3Ljw5VucTZslv3Tlt+V/EK1V8Q8evD8HMQ0dc=","encryptedInvoiceSize":6496,"encryptedInvoiceContent":"...","offlineMode":false}; // \NetSeven\KseF2Model\SendInvoiceRequest | Dane faktury

try {
    $result = $apiInstance->apiV2SessionsOnlineReferenceNumberInvoicesPost($reference_number, $send_invoice_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WysykaInteraktywnaApi->apiV2SessionsOnlineReferenceNumberInvoicesPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny sesji | |
| **send_invoice_request** | [**\NetSeven\KseF2Model\SendInvoiceRequest**](../Model/SendInvoiceRequest.md)| Dane faktury | [optional] |

### Return type

[**\NetSeven\KseF2Model\SendInvoiceResponse**](../Model/SendInvoiceResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
