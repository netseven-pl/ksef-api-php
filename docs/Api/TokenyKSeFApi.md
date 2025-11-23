# NetSeven\TokenyKSeFApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2TokensGet()**](TokenyKSeFApi.md#apiV2TokensGet) | **GET** /api/v2/tokens | Pobranie listy wygenerowanych tokenów |
| [**apiV2TokensPost()**](TokenyKSeFApi.md#apiV2TokensPost) | **POST** /api/v2/tokens | Wygenerowanie nowego tokena |
| [**apiV2TokensReferenceNumberDelete()**](TokenyKSeFApi.md#apiV2TokensReferenceNumberDelete) | **DELETE** /api/v2/tokens/{referenceNumber} | Unieważnienie tokena |
| [**apiV2TokensReferenceNumberGet()**](TokenyKSeFApi.md#apiV2TokensReferenceNumberGet) | **GET** /api/v2/tokens/{referenceNumber} | Pobranie statusu tokena |


## `apiV2TokensGet()`

```php
apiV2TokensGet($status, $description, $author_identifier, $author_identifier_type, $page_size, $x_continuation_token): \NetSeven\KseF2Model\QueryTokensResponse
```

Pobranie listy wygenerowanych tokenów

**Sortowanie:**  - dateCreated (Desc)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\TokenyKSeFApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$status = array(new \NetSeven\KseF2Model\\NetSeven\KseF2Model\AuthenticationTokenStatus()); // \NetSeven\KseF2Model\AuthenticationTokenStatus[] | Status tokenów do zwrócenia. W przypadku braku parametru zwracane są wszystkie tokeny. Parametr można przekazać wielokrotnie. | Wartość | Opis | | --- | --- | | Pending | Token został utworzony ale jest jeszcze w trakcie aktywacji i nadawania uprawnień. Nie może być jeszcze wykorzystywany do uwierzytelniania. | | Active | Token jest aktywny i może być wykorzystywany do uwierzytelniania. | | Revoking | Token jest w trakcie unieważniania. Nie może już być wykorzystywany do uwierzytelniania. | | Revoked | Token został unieważniony i nie może być wykorzystywany do uwierzytelniania. | | Failed | Nie udało się aktywować tokena. Należy wygenerować nowy token, obecny nie może być wykorzystywany do uwierzytelniania. |
$description = 'description_example'; // string | Umożliwia filtrowanie tokenów po opisie. Wartość parametru jest wyszukiwana w opisie tokena (operacja nie rozróżnia wielkości liter). Należy podać co najmniej 3 znaki.
$author_identifier = 'author_identifier_example'; // string | Umożliwia filtrowanie tokenów po ich twórcy. Wartość parametru jest wyszukiwana w identyfikatorze (operacja nie rozróżnia wielkości liter). Należy podać co najmniej 3 znaki.
$author_identifier_type = new \NetSeven\KseF2Model\\NetSevenKseF2ModelTokenAuthorIdentifierType(); // \NetSevenKseF2ModelTokenAuthorIdentifierType | Umożliwia filtrowanie tokenów po ich twórcy. Wartość parametru określa typ identyfikatora w którym będzie wyszukiwany ciąg znaków przekazany w parametrze `authorIdentifier`. | Wartość | Opis | | --- | --- | | Nip | NIP. | | Pesel | PESEL. | | Fingerprint | Odcisk palca certyfikatu. |
$page_size = 10; // int | Rozmiar strony wyników.
$x_continuation_token = 'x_continuation_token_example'; // string | Token służący do pobrania kolejnej strony wyników.

try {
    $result = $apiInstance->apiV2TokensGet($status, $description, $author_identifier, $author_identifier_type, $page_size, $x_continuation_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TokenyKSeFApi->apiV2TokensGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **status** | [**\NetSeven\KseF2Model\AuthenticationTokenStatus[]**](../Model/\NetSeven\KseF2Model\AuthenticationTokenStatus.md)| Status tokenów do zwrócenia. W przypadku braku parametru zwracane są wszystkie tokeny. Parametr można przekazać wielokrotnie. | Wartość | Opis | | --- | --- | | Pending | Token został utworzony ale jest jeszcze w trakcie aktywacji i nadawania uprawnień. Nie może być jeszcze wykorzystywany do uwierzytelniania. | | Active | Token jest aktywny i może być wykorzystywany do uwierzytelniania. | | Revoking | Token jest w trakcie unieważniania. Nie może już być wykorzystywany do uwierzytelniania. | | Revoked | Token został unieważniony i nie może być wykorzystywany do uwierzytelniania. | | Failed | Nie udało się aktywować tokena. Należy wygenerować nowy token, obecny nie może być wykorzystywany do uwierzytelniania. | | [optional] |
| **description** | **string**| Umożliwia filtrowanie tokenów po opisie. Wartość parametru jest wyszukiwana w opisie tokena (operacja nie rozróżnia wielkości liter). Należy podać co najmniej 3 znaki. | [optional] |
| **author_identifier** | **string**| Umożliwia filtrowanie tokenów po ich twórcy. Wartość parametru jest wyszukiwana w identyfikatorze (operacja nie rozróżnia wielkości liter). Należy podać co najmniej 3 znaki. | [optional] |
| **author_identifier_type** | [**\NetSevenKseF2ModelTokenAuthorIdentifierType**](../Model/.md)| Umożliwia filtrowanie tokenów po ich twórcy. Wartość parametru określa typ identyfikatora w którym będzie wyszukiwany ciąg znaków przekazany w parametrze &#x60;authorIdentifier&#x60;. | Wartość | Opis | | --- | --- | | Nip | NIP. | | Pesel | PESEL. | | Fingerprint | Odcisk palca certyfikatu. | | [optional] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **x_continuation_token** | **string**| Token służący do pobrania kolejnej strony wyników. | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryTokensResponse**](../Model/QueryTokensResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2TokensPost()`

```php
apiV2TokensPost($generate_token_request): \NetSeven\KseF2Model\GenerateTokenResponse
```

Wygenerowanie nowego tokena

Zwraca token, który może być użyty do uwierzytelniania się w KSeF.  Token może być generowany tylko w kontekście NIP lub identyfikatora wewnętrznego. Jest zwracany tylko raz. Zaczyna być aktywny w momencie gdy jego status zmieni się na `Active`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\TokenyKSeFApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$generate_token_request = {"permissions":["InvoiceRead","InvoiceWrite"],"description":"Wystawianie i przeglądanie faktur."}; // \NetSeven\KseF2Model\GenerateTokenRequest

try {
    $result = $apiInstance->apiV2TokensPost($generate_token_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TokenyKSeFApi->apiV2TokensPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **generate_token_request** | [**\NetSeven\KseF2Model\GenerateTokenRequest**](../Model/GenerateTokenRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\GenerateTokenResponse**](../Model/GenerateTokenResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2TokensReferenceNumberDelete()`

```php
apiV2TokensReferenceNumberDelete($reference_number)
```

Unieważnienie tokena

Unieważniony token nie pozwoli już na uwierzytelnienie się za jego pomocą. Unieważnienie nie może zostać cofnięte.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\TokenyKSeFApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny tokena KSeF.

try {
    $apiInstance->apiV2TokensReferenceNumberDelete($reference_number);
} catch (Exception $e) {
    echo 'Exception when calling TokenyKSeFApi->apiV2TokensReferenceNumberDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny tokena KSeF. | |

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

## `apiV2TokensReferenceNumberGet()`

```php
apiV2TokensReferenceNumberGet($reference_number): \NetSeven\KseF2Model\TokenStatusResponse
```

Pobranie statusu tokena

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\TokenyKSeFApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny tokena KSeF.

try {
    $result = $apiInstance->apiV2TokensReferenceNumberGet($reference_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TokenyKSeFApi->apiV2TokensReferenceNumberGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny tokena KSeF. | |

### Return type

[**\NetSeven\KseF2Model\TokenStatusResponse**](../Model/TokenStatusResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
