# NetSeven\CertyfikatyApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2CertificatesCertificateSerialNumberRevokePost()**](CertyfikatyApi.md#apiV2CertificatesCertificateSerialNumberRevokePost) | **POST** /api/v2/certificates/{certificateSerialNumber}/revoke | Unieważnienie certyfikatu |
| [**apiV2CertificatesEnrollmentsDataGet()**](CertyfikatyApi.md#apiV2CertificatesEnrollmentsDataGet) | **GET** /api/v2/certificates/enrollments/data | Pobranie danych do wniosku certyfikacyjnego |
| [**apiV2CertificatesEnrollmentsPost()**](CertyfikatyApi.md#apiV2CertificatesEnrollmentsPost) | **POST** /api/v2/certificates/enrollments | Wysyłka wniosku certyfikacyjnego |
| [**apiV2CertificatesEnrollmentsReferenceNumberGet()**](CertyfikatyApi.md#apiV2CertificatesEnrollmentsReferenceNumberGet) | **GET** /api/v2/certificates/enrollments/{referenceNumber} | Pobranie statusu przetwarzania wniosku certyfikacyjnego |
| [**apiV2CertificatesLimitsGet()**](CertyfikatyApi.md#apiV2CertificatesLimitsGet) | **GET** /api/v2/certificates/limits | Pobranie danych o limitach certyfikatów |
| [**apiV2CertificatesQueryPost()**](CertyfikatyApi.md#apiV2CertificatesQueryPost) | **POST** /api/v2/certificates/query | Pobranie listy metadanych certyfikatów |
| [**apiV2CertificatesRetrievePost()**](CertyfikatyApi.md#apiV2CertificatesRetrievePost) | **POST** /api/v2/certificates/retrieve | Pobranie certyfikatu lub listy certyfikatów |


## `apiV2CertificatesCertificateSerialNumberRevokePost()`

```php
apiV2CertificatesCertificateSerialNumberRevokePost($certificate_serial_number, $revoke_certificate_request)
```

Unieważnienie certyfikatu

Unieważnia certyfikat o podanym numerze seryjnym.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$certificate_serial_number = 'certificate_serial_number_example'; // string | Numer seryjny certyfikatu (w formacie szesnastkowym).
$revoke_certificate_request = new \NetSeven\KseF2Model\RevokeCertificateRequest(); // \NetSeven\KseF2Model\RevokeCertificateRequest | 

try {
    $apiInstance->apiV2CertificatesCertificateSerialNumberRevokePost($certificate_serial_number, $revoke_certificate_request);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesCertificateSerialNumberRevokePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **certificate_serial_number** | **string**| Numer seryjny certyfikatu (w formacie szesnastkowym). | |
| **revoke_certificate_request** | [**\NetSeven\KseF2Model\RevokeCertificateRequest**](../Model/RevokeCertificateRequest.md)|  | [optional] |

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

## `apiV2CertificatesEnrollmentsDataGet()`

```php
apiV2CertificatesEnrollmentsDataGet(): \NetSeven\KseF2Model\CertificateEnrollmentDataResponse
```

Pobranie danych do wniosku certyfikacyjnego

Zwraca dane wymagane do przygotowania wniosku certyfikacyjnego PKCS#10.  Dane te są zwracane na podstawie certyfikatu użytego w procesie uwierzytelnienia i identyfikują podmiot, który składa wniosek o certyfikat.   > Więcej informacji: > - [Pobranie danych do wniosku certyfikacyjnego](https://github.com/CIRFMF/ksef-docs/blob/main/certyfikaty-KSeF.md#2-pobranie-danych-do-wniosku-certyfikacyjnego) > - [Przygotowanie wniosku](https://github.com/CIRFMF/ksef-docs/blob/main/certyfikaty-KSeF.md#3-przygotowanie-csr-certificate-signing-request)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2CertificatesEnrollmentsDataGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesEnrollmentsDataGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\CertificateEnrollmentDataResponse**](../Model/CertificateEnrollmentDataResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2CertificatesEnrollmentsPost()`

```php
apiV2CertificatesEnrollmentsPost($enroll_certificate_request): \NetSeven\KseF2Model\EnrollCertificateResponse
```

Wysyłka wniosku certyfikacyjnego

Przyjmuje wniosek certyfikacyjny i rozpoczyna jego przetwarzanie.  Dozwolone typy kluczy prywatnych: - RSA (OID: 1.2.840.113549.1.1.1), długość klucza równa 2048 bitów, - EC (klucze oparte na krzywych eliptycznych, OID: 1.2.840.10045.2.1), krzywa NIST P-256 (secp256r1)  Zalecane jest stosowanie kluczy EC.  Dozwolone algorytmy podpisu: - RSA PKCS#1 v1.5, - RSA PSS, - ECDSA (format podpisu zgodny z RFC 3279)  Dozwolone funkcje skrótu użyte do podpisu CSR: - SHA1, - SHA256, - SHA384, - SHA512  > Więcej informacji: > - [Wysłanie wniosku certyfikacyjnego](https://github.com/CIRFMF/ksef-docs/blob/main/certyfikaty-KSeF.md#4-wys%C5%82anie-wniosku-certyfikacyjnego)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$enroll_certificate_request = {"certificateName":"Certyfikat-Auth-004","certificateType":"Authentication","csr":"MIIDJjCCAd4CAQAwgbAxIjAgBgNVBAMMGUZpcm1hIEtvd2Fsc2tpIENlcnR5ZmlrYXQxIjAgBgNVBAoMGUZpcm1hIEtvd2Fsc2tpIFNwLiB6IG8uby4xEzARBgNVBGEMCjc3NjI4MTE2OTIxCzAJBgNVBAYTAlBMMRUwEwYDVQQFEwxBQkMxMjM0NTY3ODkxLTArBgNVBC0MJGQ5ZDIyNzI0LTQ2OTYtNDYwYy05ZTVlLWI5ZTNhYWZiMGFmMzCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBANZC1hJiB4ZBsxGy/a4yvtOUP0HQxDt7EUZrfKO78+cmI7KCO9aW96yr6O0R928/Y9vmymbgh6KvMUTzZZj24uyxar849O1laor5t8Wv63RDx/I4+9Rt7w+QPPofmpenOokJH+Fm+FDQwo2l07o8SppGfaZpvMak+cDSrh+73wfM37fvPImr9p4ckzzxA9q6f4uoqGqcGSDlSwRjfLQKzWZaEklpZBpY4jeCh54uN3+YLsMQYKdcIbW0Jart1UbwMd/wbHfzFhVmPGOAMMpwVEBw6E4A0CTWIiAX3Alqbx4+IkuqC+gEs3ETTec7eOqhxe9V9cywi7WR+Mz6JO6DJcUCAwEAAaAAMD0GCSqGSIb3DQEBCjAwoA0wCwYJYIZIAWUDBAIBoRowGAYJKoZIhvcNAQEIMAsGCWCGSAFlAwQCAaIDAgEgA4IBAQCJhtF2/2E+JmkWitE/BGbm3NU4fIxr1Z+w0UnHsP+F8n9UDwAnuncG1GH5wZFervldEMooegzEDnYaqxnEUnbZ4wxeAHqpbTZjOOfqrk7o0r66+mXUs5NnyD4M3j3ig98GcvhEdbcNH+RsIwi7FaLNXnOE4SLYL9KvW0geriywWjS+5MmA0Gcn1e4vCD6FeEls8EHzkhrWE+rUsoM5zT2a0OPNXG3fScyOqOZe+OdjT4Y7ScRGy711u3v2X9RoTqQUDfCJ3cob/KRcrzvs1TQVazGZPfcIa6an6SigUvZ7XAMHlUTyOeM4AwKqiEqQ0qfe/HhlDylgZSwulb9u0utT","validFrom":"2025-08-28T09:22:13.388+00:00"}; // \NetSeven\KseF2Model\EnrollCertificateRequest | 

try {
    $result = $apiInstance->apiV2CertificatesEnrollmentsPost($enroll_certificate_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesEnrollmentsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **enroll_certificate_request** | [**\NetSeven\KseF2Model\EnrollCertificateRequest**](../Model/EnrollCertificateRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\EnrollCertificateResponse**](../Model/EnrollCertificateResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2CertificatesEnrollmentsReferenceNumberGet()`

```php
apiV2CertificatesEnrollmentsReferenceNumberGet($reference_number): \NetSeven\KseF2Model\CertificateEnrollmentStatusResponse
```

Pobranie statusu przetwarzania wniosku certyfikacyjnego

Zwraca informacje o statusie wniosku certyfikacyjnego.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny wniosku certyfikacyjnego

try {
    $result = $apiInstance->apiV2CertificatesEnrollmentsReferenceNumberGet($reference_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesEnrollmentsReferenceNumberGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny wniosku certyfikacyjnego | |

### Return type

[**\NetSeven\KseF2Model\CertificateEnrollmentStatusResponse**](../Model/CertificateEnrollmentStatusResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2CertificatesLimitsGet()`

```php
apiV2CertificatesLimitsGet(): \NetSeven\KseF2Model\CertificateLimitsResponse
```

Pobranie danych o limitach certyfikatów

Zwraca informacje o limitach certyfikatów oraz informacje czy użytkownik może zawnioskować o certyfikat KSeF.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2CertificatesLimitsGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesLimitsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\CertificateLimitsResponse**](../Model/CertificateLimitsResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2CertificatesQueryPost()`

```php
apiV2CertificatesQueryPost($page_size, $page_offset, $query_certificates_request): \NetSeven\KseF2Model\QueryCertificatesResponse
```

Pobranie listy metadanych certyfikatów

Zwraca listę certyfikatów spełniających podane kryteria wyszukiwania. W przypadku braku podania kryteriów wyszukiwania zwrócona zostanie nieprzefiltrowana lista.  **Sortowanie:**  - requestDate (Desc)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_size = 10; // int | Rozmiar strony wyników
$page_offset = 0; // int | Numer strony wyników
$query_certificates_request = {"type":"Offline","status":"Active"}; // \NetSeven\KseF2Model\QueryCertificatesRequest | Kryteria filtrowania

try {
    $result = $apiInstance->apiV2CertificatesQueryPost($page_size, $page_offset, $query_certificates_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesQueryPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_size** | **int**| Rozmiar strony wyników | [optional] [default to 10] |
| **page_offset** | **int**| Numer strony wyników | [optional] [default to 0] |
| **query_certificates_request** | [**\NetSeven\KseF2Model\QueryCertificatesRequest**](../Model/QueryCertificatesRequest.md)| Kryteria filtrowania | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryCertificatesResponse**](../Model/QueryCertificatesResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2CertificatesRetrievePost()`

```php
apiV2CertificatesRetrievePost($retrieve_certificates_request): \NetSeven\KseF2Model\RetrieveCertificatesResponse
```

Pobranie certyfikatu lub listy certyfikatów

Zwraca certyfikaty o podanych numerach seryjnych w formacie DER zakodowanym w Base64.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\CertyfikatyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$retrieve_certificates_request = {"certificateSerialNumbers":["0321C82DA41B4362","0321F21DA462A362"]}; // \NetSeven\KseF2Model\RetrieveCertificatesRequest | 

try {
    $result = $apiInstance->apiV2CertificatesRetrievePost($retrieve_certificates_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CertyfikatyApi->apiV2CertificatesRetrievePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **retrieve_certificates_request** | [**\NetSeven\KseF2Model\RetrieveCertificatesRequest**](../Model/RetrieveCertificatesRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\RetrieveCertificatesResponse**](../Model/RetrieveCertificatesResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
