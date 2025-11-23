# NetSeven\WyszukiwanieNadanychUprawnieApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2PermissionsQueryAuthorizationsGrantsPost()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQueryAuthorizationsGrantsPost) | **POST** /api/v2/permissions/query/authorizations/grants | Pobranie listy uprawnień podmiotowych do obsługi faktur |
| [**apiV2PermissionsQueryEntitiesRolesGet()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQueryEntitiesRolesGet) | **GET** /api/v2/permissions/query/entities/roles | Pobranie listy ról podmiotu |
| [**apiV2PermissionsQueryEuEntitiesGrantsPost()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQueryEuEntitiesGrantsPost) | **POST** /api/v2/permissions/query/eu-entities/grants | Pobranie listy uprawnień administratorów lub reprezentantów podmiotów unijnych uprawnionych do samofakturowania |
| [**apiV2PermissionsQueryPersonalGrantsPost()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQueryPersonalGrantsPost) | **POST** /api/v2/permissions/query/personal/grants | Pobranie listy własnych uprawnień |
| [**apiV2PermissionsQueryPersonsGrantsPost()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQueryPersonsGrantsPost) | **POST** /api/v2/permissions/query/persons/grants | Pobranie listy uprawnień do pracy w KSeF nadanych osobom fizycznym lub podmiotom |
| [**apiV2PermissionsQuerySubordinateEntitiesRolesPost()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQuerySubordinateEntitiesRolesPost) | **POST** /api/v2/permissions/query/subordinate-entities/roles | Pobranie listy podmiotów podrzędnych |
| [**apiV2PermissionsQuerySubunitsGrantsPost()**](WyszukiwanieNadanychUprawnieApi.md#apiV2PermissionsQuerySubunitsGrantsPost) | **POST** /api/v2/permissions/query/subunits/grants | Pobranie listy uprawnień administratorów jednostek i podmiotów podrzędnych |


## `apiV2PermissionsQueryAuthorizationsGrantsPost()`

```php
apiV2PermissionsQueryAuthorizationsGrantsPost($page_offset, $page_size, $entity_authorization_permissions_query_request): \NetSeven\KseF2Model\QueryEntityAuthorizationPermissionsResponse
```

Pobranie listy uprawnień podmiotowych do obsługi faktur

Metoda pozwala na odczytanie uprawnień podmiotowych:    - otrzymanych przez podmiot bieżącego kontekstu    - nadanych przez podmiot bieżącego kontekstu     Wybór listy nadanych lub otrzymanych uprawnień odbywa się przy użyciu parametru **queryType**.     Uprawnienia zwracane przez operację obejmują:    - **SelfInvoicing** – wystawianie faktur w trybie samofakturowania    - **TaxRepresentative** – wykonywanie operacji przedstawiciela podatkowego    - **RRInvoicing** – wystawianie faktur VAT RR    - **PefInvoicing** – wystawianie faktur PEF     Odpowiedź może być filtrowana na podstawie następujących parametrów:    - **authorizingIdentifier** – identyfikator podmiotu uprawniającego (stosowane przy queryType = Received)    - **authorizedIdentifier** – identyfikator podmiotu uprawnionego (stosowane przy queryType = Granted)    - **permissionTypes** – lista rodzajów wyszukiwanych uprawnień    #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.   > Więcej informacji:  > - [Pobieranie listy uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-uprawnie%C5%84-podmiotowych-do-obs%C5%82ugi-faktur)  **Sortowanie:**  - startDate (Desc)    **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.
$entity_authorization_permissions_query_request = {"authorizedIdentifier":{"type":"Nip","value":"7762811692"},"queryType":"Granted","permissionTypes":["SelfInvoicing","TaxRepresentative","RRInvoicing"]}; // \NetSeven\KseF2Model\EntityAuthorizationPermissionsQueryRequest

try {
    $result = $apiInstance->apiV2PermissionsQueryAuthorizationsGrantsPost($page_offset, $page_size, $entity_authorization_permissions_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQueryAuthorizationsGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **entity_authorization_permissions_query_request** | [**\NetSeven\KseF2Model\EntityAuthorizationPermissionsQueryRequest**](../Model/EntityAuthorizationPermissionsQueryRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryEntityAuthorizationPermissionsResponse**](../Model/QueryEntityAuthorizationPermissionsResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsQueryEntitiesRolesGet()`

```php
apiV2PermissionsQueryEntitiesRolesGet($page_offset, $page_size): \NetSeven\KseF2Model\QueryEntityRolesResponse
```

Pobranie listy ról podmiotu

Metoda pozwala na **odczytanie listy ról podmiotu bieżącego kontekstu logowania**.  #### Role podmiotów zwracane przez operację: - **CourtBailiff** – komornik sądowy   - **EnforcementAuthority** – organ egzekucyjny   - **LocalGovernmentUnit** – nadrzędna JST   - **LocalGovernmentSubUnit** – podrzędne JST   - **VatGroupUnit** – grupa VAT   - **VatGroupSubUnit** – członek grupy VAT  #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.    > Więcej informacji:  > - [Pobieranie listy ról](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-r%C3%B3l-podmiotu)  **Sortowanie:**  - startDate (Desc)    **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.

try {
    $result = $apiInstance->apiV2PermissionsQueryEntitiesRolesGet($page_offset, $page_size);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQueryEntitiesRolesGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |

### Return type

[**\NetSeven\KseF2Model\QueryEntityRolesResponse**](../Model/QueryEntityRolesResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsQueryEuEntitiesGrantsPost()`

```php
apiV2PermissionsQueryEuEntitiesGrantsPost($page_offset, $page_size, $eu_entity_permissions_query_request): \NetSeven\KseF2Model\QueryEuEntityPermissionsResponse
```

Pobranie listy uprawnień administratorów lub reprezentantów podmiotów unijnych uprawnionych do samofakturowania

Metoda pozwala na odczytanie uprawnień administratorów lub reprezentantów podmiotów unijnych:    - Jeżeli kontekstem logowania jest NIP, możliwe jest odczytanie uprawnień administratorów podmiotów unijnych powiązanych z podmiotem bieżącego kontekstu, czyli takich, dla których pierwszy człon kontekstu złożonego jest równy NIP-owi kontekstu logowania.    - Jeżeli kontekst logowania jest złożony (NIP-VAT UE), możliwe jest pobranie wszystkich uprawnień administratorów i reprezentantów podmiotu w bieżącym kontekście złożonym.     Uprawnienia zwracane przez operację obejmują:    - **VatUeManage** – zarządzanie uprawnieniami w ramach podmiotu unijnego    - **InvoiceWrite** – wystawianie faktur    - **InvoiceRead** – przeglądanie faktur    - **Introspection** – przeglądanie historii sesji     Odpowiedź może być filtrowana na podstawie następujących parametrów:    - **vatUeIdentifier** – identyfikator podmiotu unijnego    - **authorizedFingerprintIdentifier** – odcisk palca certyfikatu uprawnionej osoby lub podmiotu    - **permissionTypes** – lista rodzajów wyszukiwanych uprawnień    #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.    > Więcej informacji:  > - [Pobieranie listy uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-uprawnie%C5%84-administrator%C3%B3w-lub-reprezentant%C3%B3w-podmiot%C3%B3w-unijnych-uprawnionych-do-samofakturowania)  **Sortowanie:**  - startDate (Desc)    **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`, `VatUeManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.
$eu_entity_permissions_query_request = {"vatUeIdentifier":"DE123456789012","permissionTypes":["VatUeManage","Introspection"]}; // \NetSeven\KseF2Model\EuEntityPermissionsQueryRequest

try {
    $result = $apiInstance->apiV2PermissionsQueryEuEntitiesGrantsPost($page_offset, $page_size, $eu_entity_permissions_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQueryEuEntitiesGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **eu_entity_permissions_query_request** | [**\NetSeven\KseF2Model\EuEntityPermissionsQueryRequest**](../Model/EuEntityPermissionsQueryRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryEuEntityPermissionsResponse**](../Model/QueryEuEntityPermissionsResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsQueryPersonalGrantsPost()`

```php
apiV2PermissionsQueryPersonalGrantsPost($page_offset, $page_size, $personal_permissions_query_request): \NetSeven\KseF2Model\QueryPersonalPermissionsResponse
```

Pobranie listy własnych uprawnień

Metoda pozwala na odczytanie własnych uprawnień uwierzytelnionego klienta API w bieżącym kontekście logowania.     W odpowiedzi przekazywane są następujące uprawnienia:    - nadane w sposób bezpośredni w bieżącym kontekście    - nadane przez podmiot nadrzędny    - nadane w sposób pośredni, jeżeli podmiot kontekstu logowania jest w uprawnieniu pośrednikiem lub podmiotem docelowym    - nadane podmiotowi do obsługi faktur przez inny podmiot, jeśli podmiot uwierzytelniony ma w bieżącym kontekście uprawnienia właścicielskie     Uprawnienia zwracane przez operację obejmują:    - **CredentialsManage** – zarządzanie uprawnieniami    - **CredentialsRead** – przeglądanie uprawnień    - **InvoiceWrite** – wystawianie faktur    - **InvoiceRead** – przeglądanie faktur    - **Introspection** – przeglądanie historii sesji    - **SubunitManage** – zarządzanie podmiotami podrzędnymi    - **EnforcementOperations** – wykonywanie operacji egzekucyjnych    - **VatEuManage** – zarządzanie uprawnieniami w ramach podmiotu unijnego     Odpowiedź może być filtrowana na podstawie następujących parametrów:    - **contextIdentifier** – identyfikator podmiotu, który nadał uprawnienie do obsługi faktur    - **targetIdentifier** – identyfikator podmiotu docelowego dla uprawnień nadanych pośrednio    - **permissionTypes** – lista rodzajów wyszukiwanych uprawnień    - **permissionState** – status uprawnienia    #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.   > Więcej informacji:  > - [Pobieranie listy uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-w%C5%82asnych-uprawnie%C5%84)  **Sortowanie:**  - startDate (Desc)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.
$personal_permissions_query_request = {"contextIdentifier":{"type":"Nip","value":"3568707925"},"permissionTypes":["InvoiceWrite"],"permissionState":"Active"}; // \NetSeven\KseF2Model\PersonalPermissionsQueryRequest

try {
    $result = $apiInstance->apiV2PermissionsQueryPersonalGrantsPost($page_offset, $page_size, $personal_permissions_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQueryPersonalGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **personal_permissions_query_request** | [**\NetSeven\KseF2Model\PersonalPermissionsQueryRequest**](../Model/PersonalPermissionsQueryRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryPersonalPermissionsResponse**](../Model/QueryPersonalPermissionsResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsQueryPersonsGrantsPost()`

```php
apiV2PermissionsQueryPersonsGrantsPost($page_offset, $page_size, $person_permissions_query_request): \NetSeven\KseF2Model\QueryPersonPermissionsResponse
```

Pobranie listy uprawnień do pracy w KSeF nadanych osobom fizycznym lub podmiotom

Metoda pozwala na odczytanie uprawnień nadanych osobie fizycznej lub podmiotowi.    Lista pobranych uprawnień może być dwóch rodzajów:    - Lista wszystkich uprawnień obowiązujących w bieżącym kontekście logowania (używana, gdy administrator chce przejrzeć uprawnienia wszystkich użytkowników w bieżącym kontekście)    - Lista wszystkich uprawnień nadanych w bieżącym kontekście przez uwierzytelnionego klienta API (używana, gdy administrator chce przejrzeć listę nadanych przez siebie uprawnień w bieżącym kontekście)     Dla pierwszej listy (obowiązujących uprawnień) w odpowiedzi przekazywane są:    - osoby i podmioty mogące pracować w bieżącym kontekście z wyjątkiem osób uprawnionych w sposób pośredni    - osoby uprawnione w sposób pośredni przez podmiot bieżącego kontekstu     Dla drugiej listy (nadanych uprawnień) w odpowiedzi przekazywane są:    - uprawnienia nadane w sposób bezpośredni do pracy w bieżącym kontekście lub w kontekście jednostek podrzędnych    - uprawnienia nadane w sposób pośredni do obsługi klientów podmiotu bieżącego kontekstu     Uprawnienia zwracane przez operację obejmują:    - **CredentialsManage** – zarządzanie uprawnieniami    - **CredentialsRead** – przeglądanie uprawnień    - **InvoiceWrite** – wystawianie faktur    - **InvoiceRead** – przeglądanie faktur    - **Introspection** – przeglądanie historii sesji    - **SubunitManage** – zarządzanie podmiotami podrzędnymi    - **EnforcementOperations** – wykonywanie operacji egzekucyjnych     Odpowiedź może być filtrowana na podstawie parametrów:    - **authorIdentifier** – identyfikator osoby, która nadała uprawnienie    - **authorizedIdentifier** – identyfikator osoby lub podmiotu uprawnionego    - **targetIdentifier** – identyfikator podmiotu docelowego dla uprawnień nadanych pośrednio    - **permissionTypes** – lista rodzajów wyszukiwanych uprawnień    - **permissionState** – status uprawnienia    - **queryType** – typ zapytania określający, która z dwóch list ma zostać zwrócona    #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.   > Więcej informacji:  > - [Pobieranie listy uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-uprawnie%C5%84-do-pracy-w-ksef-nadanych-osobom-fizycznym-lub-podmiotom)  **Sortowanie:**  - startDate (Desc)    **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`, `SubunitManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.
$person_permissions_query_request = {"authorIdentifier":{"type":"Nip","value":"7762811692"},"permissionTypes":["CredentialsManage","CredentialsRead","InvoiceWrite"],"permissionState":"Active","queryType":"PermissionsInCurrentContext"}; // \NetSeven\KseF2Model\PersonPermissionsQueryRequest

try {
    $result = $apiInstance->apiV2PermissionsQueryPersonsGrantsPost($page_offset, $page_size, $person_permissions_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQueryPersonsGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **person_permissions_query_request** | [**\NetSeven\KseF2Model\PersonPermissionsQueryRequest**](../Model/PersonPermissionsQueryRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryPersonPermissionsResponse**](../Model/QueryPersonPermissionsResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsQuerySubordinateEntitiesRolesPost()`

```php
apiV2PermissionsQuerySubordinateEntitiesRolesPost($page_offset, $page_size, $subordinate_entity_roles_query_request): \NetSeven\KseF2Model\QuerySubordinateEntityRolesResponse
```

Pobranie listy podmiotów podrzędnych

Metoda pozwala na odczytanie listy podmiotów podrzędnych,    jeżeli podmiot bieżącego kontekstu ma rolę podmiotu nadrzędnego:  - **nadrzędna JST** – odczytywane są podrzędne JST,    - **grupa VAT** – odczytywane są podmioty będące członkami grupy VAT.   Role podmiotów zwracane przez operację obejmują:    - **LocalGovernmentSubUnit** – podrzędne JST,    - **VatGroupSubUnit** – członek grupy VAT.   Odpowiedź może być filtrowana według parametru:    - **subordinateEntityIdentifier** – identyfikator podmiotu podrzędnego.  #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.     > Więcej informacji:  > - [Pobieranie listy podmiotów podrzędnych](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-podmiot%C3%B3w-podrz%C4%99dnych)  **Sortowanie:**  - startDate (Desc)    **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`, `SubunitManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.
$subordinate_entity_roles_query_request = {"subordinateEntityIdentifier":{"type":"Nip","value":"7762811692"}}; // \NetSeven\KseF2Model\SubordinateEntityRolesQueryRequest

try {
    $result = $apiInstance->apiV2PermissionsQuerySubordinateEntitiesRolesPost($page_offset, $page_size, $subordinate_entity_roles_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQuerySubordinateEntitiesRolesPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **subordinate_entity_roles_query_request** | [**\NetSeven\KseF2Model\SubordinateEntityRolesQueryRequest**](../Model/SubordinateEntityRolesQueryRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\QuerySubordinateEntityRolesResponse**](../Model/QuerySubordinateEntityRolesResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2PermissionsQuerySubunitsGrantsPost()`

```php
apiV2PermissionsQuerySubunitsGrantsPost($page_offset, $page_size, $subunit_permissions_query_request): \NetSeven\KseF2Model\QuerySubunitPermissionsResponse
```

Pobranie listy uprawnień administratorów jednostek i podmiotów podrzędnych

Metoda pozwala na odczytanie uprawnień do zarządzania uprawnieniami nadanych administratorom:    - jednostek podrzędnych identyfikowanych identyfikatorem wewnętrznym    - podmiotów podrzędnych (podrzędnych JST lub członków grupy VAT) identyfikowanych przez NIP     Lista zwraca wyłącznie uprawnienia do zarządzania uprawnieniami nadane z kontekstu bieżącego (z podmiotu nadrzędnego).    Nie są odczytywane uprawnienia nadane przez administratorów jednostek podrzędnych wewnątrz tych jednostek.     Odpowiedź może być filtrowana na podstawie parametru:    - **subunitIdentifier** – identyfikator jednostki lub podmiotu podrzędnego    #### Stronicowanie wyników Zapytanie zwraca **jedną stronę wyników** o numerze i rozmiarze podanym w ścieżce. - Przy pierwszym wywołaniu należy ustawić parametr `pageOffset = 0`.   - Jeżeli dostępna jest kolejna strona wyników, w odpowiedzi pojawi się flaga **`hasMore`**.   - W takim przypadku można wywołać zapytanie ponownie z kolejnym numerem strony.   > Więcej informacji:  > - [Pobieranie listy uprawnień](https://github.com/CIRFMF/ksef-docs/blob/main/uprawnienia.md#pobranie-listy-uprawnie%C5%84-administrator%C3%B3w-jednostek-i-podmiot%C3%B3w-podrz%C4%99dnych)  **Sortowanie:**  - startDate (Desc)    **Wymagane uprawnienia**: `CredentialsManage`, `CredentialsRead`, `SubunitManage`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\WyszukiwanieNadanychUprawnieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page_offset = 0; // int | Numer strony wyników.
$page_size = 10; // int | Rozmiar strony wyników.
$subunit_permissions_query_request = {"subunitIdentifier":{"type":"InternalId","value":"7762811692-12345"}}; // \NetSeven\KseF2Model\SubunitPermissionsQueryRequest

try {
    $result = $apiInstance->apiV2PermissionsQuerySubunitsGrantsPost($page_offset, $page_size, $subunit_permissions_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WyszukiwanieNadanychUprawnieApi->apiV2PermissionsQuerySubunitsGrantsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_offset** | **int**| Numer strony wyników. | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **subunit_permissions_query_request** | [**\NetSeven\KseF2Model\SubunitPermissionsQueryRequest**](../Model/SubunitPermissionsQueryRequest.md)|  | [optional] |

### Return type

[**\NetSeven\KseF2Model\QuerySubunitPermissionsResponse**](../Model/QuerySubunitPermissionsResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
