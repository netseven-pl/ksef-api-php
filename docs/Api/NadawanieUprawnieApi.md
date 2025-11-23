# NetSeven\NadawanieUprawnieApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2PermissionsAuthorizationsGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsAuthorizationsGrantsPost) | **POST** /api/v2/permissions/authorizations/grants | Nadanie uprawnień podmiotowych |
| [**apiV2PermissionsEntitiesGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsEntitiesGrantsPost) | **POST** /api/v2/permissions/entities/grants | Nadanie podmiotom uprawnień do obsługi faktur |
| [**apiV2PermissionsEuEntitiesAdministrationGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsEuEntitiesAdministrationGrantsPost) | **POST** /api/v2/permissions/eu-entities/administration/grants | Nadanie uprawnień administratora podmiotu unijnego |
| [**apiV2PermissionsEuEntitiesGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsEuEntitiesGrantsPost) | **POST** /api/v2/permissions/eu-entities/grants | Nadanie uprawnień reprezentanta podmiotu unijnego |
| [**apiV2PermissionsIndirectGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsIndirectGrantsPost) | **POST** /api/v2/permissions/indirect/grants | Nadanie uprawnień w sposób pośredni |
| [**apiV2PermissionsPersonsGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsPersonsGrantsPost) | **POST** /api/v2/permissions/persons/grants | Nadanie osobom fizycznym uprawnień do pracy w KSeF |
| [**apiV2PermissionsSubunitsGrantsPost()**](NadawanieUprawnieApi.md#apiV2PermissionsSubunitsGrantsPost) | **POST** /api/v2/permissions/subunits/grants | Nadanie uprawnień administratora podmiotu podrzędnego |


## `apiV2PermissionsAuthorizationsGrantsPost()`

```php
apiV2PermissionsAuthorizationsGrantsPost($entity_authorization_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie uprawnień podmiotowych

Metoda pozwala na nadanie jednego z uprawnień podmiotowych do obsługi podmiotu kontekstu  podmiotowi wskazanemu w żądaniu.  > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadanie-uprawnie%C5%84-podmiotowych)  **Wymagane uprawnienia**: `CredentialsManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$entity_authorization_permissions_grant_request = {"subjectIdentifier":{"type":"Nip","value":"7762811692"},"permission":"SelfInvoicing","description":"działanie w imieniu 3393244202 w kontekście 7762811692, Firma sp. z o.o."}; // \NetSeven\KseF2Model\EntityAuthorizationPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsAuthorizationsGrantsPost($entity_authorization_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsAuthorizationsGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **entity_authorization_permissions_grant_request** | [**\NetSeven\KseF2Model\EntityAuthorizationPermissionsGrantRequest**](../Model/EntityAuthorizationPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsEntitiesGrantsPost()`

```php
apiV2PermissionsEntitiesGrantsPost($entity_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie podmiotom uprawnień do obsługi faktur

Metoda pozwala na nadanie podmiotowi wskazanemu w żądaniu uprawnień do obsługi faktur podmiotu kontekstu.   W żądaniu określane są nadawane uprawnienia ze zbioru:   - **InvoiceWrite** – wystawianie faktur   - **InvoiceRead** – przeglądanie faktur                Metoda pozwala na wybór dowolnej kombinacji powyższych uprawnień.   Dla każdego uprawnienia może być ustawiona flaga **canDelegate**, mówiąca o możliwości jego dalszego przekazywania poprzez nadawanie w sposób pośredni.  > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadanie-podmiotom-uprawnie%C5%84-do-obs%C5%82ugi-faktur)  **Wymagane uprawnienia**: `CredentialsManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$entity_permissions_grant_request = {"subjectIdentifier":{"type":"Nip","value":"7762811692"},"permissions":[{"type":"InvoiceRead","canDelegate":true},{"type":"InvoiceWrite","canDelegate":true}],"description":"Opis uprawnienia"}; // \NetSeven\KseF2Model\EntityPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsEntitiesGrantsPost($entity_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsEntitiesGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **entity_permissions_grant_request** | [**\NetSeven\KseF2Model\EntityPermissionsGrantRequest**](../Model/EntityPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsEuEntitiesAdministrationGrantsPost()`

```php
apiV2PermissionsEuEntitiesAdministrationGrantsPost($eu_entity_administration_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie uprawnień administratora podmiotu unijnego

Metoda pozwala na nadanie wskazanemu w żądaniu podmiotowi lub osobie fizycznej uprawnień administratora w kontekście złożonym z identyfikatora NIP podmiotu kontekstu bieżącego oraz numeru VAT UE podmiotu unijnego wskazanego w żądaniu.   Wraz z utworzeniem administratora podmiotu unijnego tworzony jest kontekst złożony składający się z numeru NIP podmiotu kontekstu logowania oraz wskazanego numeru identyfikacyjnego VAT UE podmiotu unijnego.   W żądaniu podaje się również nazwę i adres podmiotu unijnego.                Jedynym sposobem identyfikacji uprawnianego jest odcisk palca certyfikatu kwalifikowanego:   - certyfikat podpisu elektronicznego dla osób fizycznych   - certyfikat pieczęci elektronicznej dla podmiotów                Uprawnienia administratora podmiotu unijnego obejmują:   - **VatEuManage** – zarządzanie uprawnieniami w ramach podmiotu unijnego   - **InvoiceWrite** – wystawianie faktur   - **InvoiceRead** – przeglądanie faktur   - **Introspection** – przeglądanie historii sesji                Metoda automatycznie nadaje wszystkie powyższe uprawnienia, bez konieczności ich wskazywania w żądaniu.              > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadanie-uprawnie%C5%84-administratora-podmiotu-unijnego)  **Wymagane uprawnienia**: `CredentialsManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$eu_entity_administration_permissions_grant_request = {"subjectIdentifier":{"type":"Fingerprint","value":"CEB3643BAC2C111ADDE971BDA5A80163441867D65389FC0BC0DFF8B4C1CD4E59"},"contextIdentifier":{"type":"NipVatUe","value":"7762811692-DE123456789012"},"description":"Opis uprawnienia","euEntityName":"Firma G.m.b.H."}; // \NetSeven\KseF2Model\EuEntityAdministrationPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsEuEntitiesAdministrationGrantsPost($eu_entity_administration_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsEuEntitiesAdministrationGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **eu_entity_administration_permissions_grant_request** | [**\NetSeven\KseF2Model\EuEntityAdministrationPermissionsGrantRequest**](../Model/EuEntityAdministrationPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsEuEntitiesGrantsPost()`

```php
apiV2PermissionsEuEntitiesGrantsPost($eu_entity_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie uprawnień reprezentanta podmiotu unijnego

Metoda pozwala na nadanie wskazanemu w żądaniu podmiotowi lub osobie fizycznej uprawnień do wystawiania i/lub przeglądania faktur w kontekście złożonym kontekstu bieżącego.                Jedynym sposobem identyfikacji uprawnianego jest odcisk palca certyfikatu kwalifikowanego:   - certyfikat podpisu elektronicznego dla osób fizycznych   - certyfikat pieczęci elektronicznej dla podmiotów                W żądaniu określane są nadawane uprawnienia ze zbioru:   - **InvoiceWrite** – wystawianie faktur   - **InvoiceRead** – przeglądanie faktur                Metoda pozwala na wybór dowolnej kombinacji powyższych uprawnień.  > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadanie-uprawnie%C5%84-reprezentanta-podmiotu-unijnego)  **Wymagane uprawnienia**: `VatUeManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$eu_entity_permissions_grant_request = {"subjectIdentifier":{"type":"Fingerprint","value":"CEB3643BAC2C111ADDE971BDA5A80163441867D65389FC0BC0DFF8B4C1CD4E59"},"permissions":["InvoiceRead","InvoiceWrite"],"description":"Opis uprawnienia"}; // \NetSeven\KseF2Model\EuEntityPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsEuEntitiesGrantsPost($eu_entity_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsEuEntitiesGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **eu_entity_permissions_grant_request** | [**\NetSeven\KseF2Model\EuEntityPermissionsGrantRequest**](../Model/EuEntityPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsIndirectGrantsPost()`

```php
apiV2PermissionsIndirectGrantsPost($indirect_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie uprawnień w sposób pośredni

Metoda pozwala na nadanie w sposób pośredni osobie wskazanej w żądaniu uprawnień do obsługi faktur innego podmiotu – klienta.   Może to być jedna z możliwości:   - nadanie uprawnień generalnych – do obsługi wszystkich klientów   - nadanie uprawnień selektywnych – do obsługi wskazanego klienta                Uprawnienie selektywne może być nadane wyłącznie wtedy, gdy klient nadał wcześniej podmiotowi bieżącego kontekstu dowolne uprawnienie z prawem do jego dalszego przekazywania (patrz [POST /api/v2/permissions/entities/grants](/docs/v2/index.html#tag/Nadawanie-uprawnien/paths/~1api~1v2~1permissions~1entities~1grants/post)).                W żądaniu określane są nadawane uprawnienia ze zbioru:   - **InvoiceWrite** – wystawianie faktur   - **InvoiceRead** – przeglądanie faktur                Metoda pozwala na wybór dowolnej kombinacji powyższych uprawnień.  > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadanie-uprawnie%C5%84-w-spos%C3%B3b-po%C5%9Bredni)  **Wymagane uprawnienia**: `CredentialsManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$indirect_permissions_grant_request = {"subjectIdentifier":{"type":"Pesel","value":"22271569167"},"targetIdentifier":{"type":"Nip","value":"5687926712"},"permissions":["InvoiceWrite","InvoiceRead"],"description":"praca dla klienta 5687926712; uprawniony PESEL: 22271569167, Adam Abacki; pośrednik 3936518395"}; // \NetSeven\KseF2Model\IndirectPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsIndirectGrantsPost($indirect_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsIndirectGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **indirect_permissions_grant_request** | [**\NetSeven\KseF2Model\IndirectPermissionsGrantRequest**](../Model/IndirectPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsPersonsGrantsPost()`

```php
apiV2PermissionsPersonsGrantsPost($person_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie osobom fizycznym uprawnień do pracy w KSeF

Metoda pozwala na nadanie osobie wskazanej w żądaniu uprawnień do pracy w KSeF   w kontekście bieżącym.              W żądaniu określane są nadawane uprawnienia ze zbioru:   - **InvoiceWrite** – wystawianie faktur,   - **InvoiceRead** – przeglądanie faktur,   - **CredentialsManage** – zarządzanie uprawnieniami,   - **CredentialsRead** – przeglądanie uprawnień,   - **Introspection** – przeglądanie historii sesji i generowanie UPO,   - **SubunitManage** – zarządzanie jednostkami podrzędnymi,   - **EnforcementOperations** – wykonywanie operacji egzekucyjnych.              Metoda pozwala na wybór dowolnej kombinacji powyższych uprawnień.   Uprawnienie **EnforcementOperations** może być nadane wyłącznie wtedy,   gdy podmiot kontekstu ma rolę **EnforcementAuthority** (organ egzekucyjny)   lub **CourtBailiff** (komornik sądowy).  > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadawanie-uprawnie%C5%84-osobom-fizycznym-do-pracy-w-ksef)  **Wymagane uprawnienia**: `CredentialsManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$person_permissions_grant_request = {"subjectIdentifier":{"type":"Pesel","value":"15062788702"},"permissions":["InvoiceRead","InvoiceWrite","Introspection","CredentialsRead"],"description":"Opis uprawnienia"}; // \NetSeven\KseF2Model\PersonPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsPersonsGrantsPost($person_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsPersonsGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **person_permissions_grant_request** | [**\NetSeven\KseF2Model\PersonPermissionsGrantRequest**](../Model/PersonPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsSubunitsGrantsPost()`

```php
apiV2PermissionsSubunitsGrantsPost($subunit_permissions_grant_request): \NetSeven\KseF2Model\PermissionsOperationResponse
```

Nadanie uprawnień administratora podmiotu podrzędnego

Metoda pozwala na nadanie wskazanemu w żądaniu podmiotowi lub osobie fizycznej uprawnień administratora w kontekście:   - wskazanego NIP podmiotu podrzędnego – wyłącznie jeżeli podmiot bieżącego kontekstu logowania ma rolę podmiotu nadrzędnego:   - **LocalGovernmentUnit**    - **VatGroupUnit**   - wskazanego lub utworzonego identyfikatora wewnętrznego                Wraz z utworzeniem administratora jednostki podrzędnej tworzony jest identyfikator wewnętrzny składający się z numeru NIP podmiotu kontekstu logowania oraz 5 cyfr unikalnie identyfikujących jednostkę wewnętrzną.   W żądaniu podaje się również nazwę tej jednostki.                Uprawnienia administratora jednostki podrzędnej obejmują:   - **CredentialsManage** – zarządzanie uprawnieniami                Metoda automatycznie nadaje powyższe uprawnienie, bez konieczności podawania go w żądaniu.              > Więcej informacji: > - [Nadawanie uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#nadanie-uprawnie%C5%84-administratora-podmiotu-podrz%C4%99dnego)  **Wymagane uprawnienia**: `SubunitManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\NadawanieUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subunit_permissions_grant_request = {"subjectIdentifier":{"type":"Pesel","value":"15062788702"},"contextIdentifier":{"type":"InternalId","value":"7762811692-12345"},"description":"Opis uprawnienia","subunitName":"Jednostka 014"}; // \NetSeven\KseF2Model\SubunitPermissionsGrantRequest

try {
    $result = $apiInstance->apiV2PermissionsSubunitsGrantsPost($subunit_permissions_grant_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NadawanieUprawnieApi->apiV2PermissionsSubunitsGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **subunit_permissions_grant_request** | [**\NetSeven\KseF2Model\SubunitPermissionsGrantRequest**](../Model/SubunitPermissionsGrantRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\PermissionsOperationResponse**](../Model/PermissionsOperationResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
