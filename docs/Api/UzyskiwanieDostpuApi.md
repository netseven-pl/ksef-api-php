# NetSeven\UzyskiwanieDostpuApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2AuthChallengePost()**](UzyskiwanieDostpuApi.md#apiV2AuthChallengePost) | **POST** /api/v2/auth/challenge | Inicjalizacja uwierzytelnienia |
| [**apiV2AuthKsefTokenPost()**](UzyskiwanieDostpuApi.md#apiV2AuthKsefTokenPost) | **POST** /api/v2/auth/ksef-token | Uwierzytelnienie z wykorzystaniem tokena KSeF |
| [**apiV2AuthReferenceNumberGet()**](UzyskiwanieDostpuApi.md#apiV2AuthReferenceNumberGet) | **GET** /api/v2/auth/{referenceNumber} | Pobranie statusu uwierzytelniania |
| [**apiV2AuthTokenRedeemPost()**](UzyskiwanieDostpuApi.md#apiV2AuthTokenRedeemPost) | **POST** /api/v2/auth/token/redeem | Pobranie tokenów dostępowych |
| [**apiV2AuthTokenRefreshPost()**](UzyskiwanieDostpuApi.md#apiV2AuthTokenRefreshPost) | **POST** /api/v2/auth/token/refresh | Odświeżenie tokena dostępowego |
| [**apiV2AuthXadesSignaturePost()**](UzyskiwanieDostpuApi.md#apiV2AuthXadesSignaturePost) | **POST** /api/v2/auth/xades-signature | Uwierzytelnienie z wykorzystaniem podpisu XAdES |


## `apiV2AuthChallengePost()`

```php
apiV2AuthChallengePost(): \NetSeven\KseF2Model\AuthenticationChallengeResponse
```

Inicjalizacja uwierzytelnienia

Generuje unikalny challenge wymagany w kolejnym kroku operacji uwierzytelnienia.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new NetSeven\Api\UzyskiwanieDostpuApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->apiV2AuthChallengePost();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UzyskiwanieDostpuApi->apiV2AuthChallengePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\AuthenticationChallengeResponse**](../Model/AuthenticationChallengeResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthKsefTokenPost()`

```php
apiV2AuthKsefTokenPost($init_token_authentication_request): \NetSeven\KseF2Model\AuthenticationInitResponse
```

Uwierzytelnienie z wykorzystaniem tokena KSeF

Rozpoczyna operację uwierzytelniania z wykorzystaniem wcześniej wygenerowanego tokena KSeF.  Token KSeF wraz z timestampem ze wcześniej wygenerowanego challenge'a (w formacie ```token|timestamp```) powinien zostać zaszyfrowany dedykowanym do tego celu kluczem publicznym. - Timestamp powinien zostać przekazany jako **liczba milisekund od 1 stycznia 1970 roku (Unix timestamp)**. - Algorytm szyfrowania: **RSA-OAEP (z użyciem SHA-256 jako funkcji skrótu)**.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new NetSeven\Api\UzyskiwanieDostpuApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$init_token_authentication_request = {"challenge":"20250625-CR-2FDC223000-C2BFC98A9C-4E","contextIdentifier":{"type":"Nip","value":"5265877635"},"encryptedToken":"..."}; // \NetSeven\KseF2Model\InitTokenAuthenticationRequest

try {
    $result = $apiInstance->apiV2AuthKsefTokenPost($init_token_authentication_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UzyskiwanieDostpuApi->apiV2AuthKsefTokenPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **init_token_authentication_request** | [**\NetSeven\KseF2Model\InitTokenAuthenticationRequest**](../Model/InitTokenAuthenticationRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\AuthenticationInitResponse**](../Model/AuthenticationInitResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthReferenceNumberGet()`

```php
apiV2AuthReferenceNumberGet($reference_number): \NetSeven\KseF2Model\AuthenticationOperationStatusResponse
```

Pobranie statusu uwierzytelniania

Sprawdza bieżący status operacji uwierzytelniania dla podanego tokena.  Sposób uwierzytelnienia: `AuthenticationToken` otrzymany przy rozpoczęciu operacji uwierzytelniania.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\UzyskiwanieDostpuApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny tokena otrzymanego przy inicjalizacji operacji uwierzytelniania.

try {
    $result = $apiInstance->apiV2AuthReferenceNumberGet($reference_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UzyskiwanieDostpuApi->apiV2AuthReferenceNumberGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny tokena otrzymanego przy inicjalizacji operacji uwierzytelniania. | |

### Return type

[**\NetSeven\KseF2Model\AuthenticationOperationStatusResponse**](../Model/AuthenticationOperationStatusResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthTokenRedeemPost()`

```php
apiV2AuthTokenRedeemPost(): \NetSeven\KseF2Model\AuthenticationTokensResponse
```

Pobranie tokenów dostępowych

Pobiera parę tokenów (access token i refresh token) wygenerowanych w ramach pozytywnie zakończonego procesu uwierzytelniania. **Tokeny można pobrać tylko raz.**  Sposób uwierzytelnienia: `AuthenticationToken` otrzymany przy rozpoczęciu operacji uwierzytelniania.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\UzyskiwanieDostpuApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2AuthTokenRedeemPost();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UzyskiwanieDostpuApi->apiV2AuthTokenRedeemPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\AuthenticationTokensResponse**](../Model/AuthenticationTokensResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthTokenRefreshPost()`

```php
apiV2AuthTokenRefreshPost(): \NetSeven\KseF2Model\AuthenticationTokenRefreshResponse
```

Odświeżenie tokena dostępowego

Generuje nowy token dostępu na podstawie ważnego refresh tokena.  Sposób uwierzytelnienia: `RefreshToken`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\UzyskiwanieDostpuApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->apiV2AuthTokenRefreshPost();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UzyskiwanieDostpuApi->apiV2AuthTokenRefreshPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\NetSeven\KseF2Model\AuthenticationTokenRefreshResponse**](../Model/AuthenticationTokenRefreshResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2AuthXadesSignaturePost()`

```php
apiV2AuthXadesSignaturePost($body, $verify_certificate_chain): \NetSeven\KseF2Model\AuthenticationInitResponse
```

Uwierzytelnienie z wykorzystaniem podpisu XAdES

Rozpoczyna operację uwierzytelniania za pomocą dokumentu XML podpisanego podpisem elektronicznym XAdES.  > Więcej informacji: > - [Przygotowanie dokumentu XML](https://github.com/CIRFMF/ksef-docs/blob/main/uwierzytelnianie.md#1-przygotowanie-dokumentu-xml-authtokenrequest) > - [Podpis dokumentu XML](https://github.com/CIRFMF/ksef-docs/blob/main/uwierzytelnianie.md#2-podpisanie-dokumentu-xades) > - [Schemat XSD](/docs/v2/schemas/authv2.xsd)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new NetSeven\Api\UzyskiwanieDostpuApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = <?xml version="1.0" encoding="utf-8"?>
<AuthTokenRequest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://ksef.mf.gov.pl/auth/token/2.0">
    <Challenge>20250625-CR-20F5EE4000-DA48AE4124-46</Challenge>
    <ContextIdentifier>
        <Nip>5265877635</Nip>
    </ContextIdentifier>
    <SubjectIdentifierType>certificateSubject</SubjectIdentifierType>
    <ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#" Id="Signature-9707709">
        <!-- Tu powinien być podpis XAdES -->
    </ds:Signature>
</AuthTokenRequest>; // string
$verify_certificate_chain = True; // bool | Wymuszenie weryfikacji zaufania łańcucha certyfikatu wraz ze sprawdzeniem statusu certyfikatu (OCSP/CRL) na środowiskach które umożliwiają wykorzystanie samodzielnie wygenerowanych certyfikatów.

try {
    $result = $apiInstance->apiV2AuthXadesSignaturePost($body, $verify_certificate_chain);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UzyskiwanieDostpuApi->apiV2AuthXadesSignaturePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **string**|  | |
| **verify_certificate_chain** | **bool**| Wymuszenie weryfikacji zaufania łańcucha certyfikatu wraz ze sprawdzeniem statusu certyfikatu (OCSP/CRL) na środowiskach które umożliwiają wykorzystanie samodzielnie wygenerowanych certyfikatów. | [optional] |

### Return type

[**\NetSeven\KseF2Model\AuthenticationInitResponse**](../Model/AuthenticationInitResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/xml`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
