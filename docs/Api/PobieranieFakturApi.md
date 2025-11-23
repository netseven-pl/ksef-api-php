# NetSeven\PobieranieFakturApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV2InvoicesExportsPost()**](PobieranieFakturApi.md#apiV2InvoicesExportsPost) | **POST** /api/v2/invoices/exports | Eksport paczki faktur |
| [**apiV2InvoicesExportsReferenceNumberGet()**](PobieranieFakturApi.md#apiV2InvoicesExportsReferenceNumberGet) | **GET** /api/v2/invoices/exports/{referenceNumber} | Pobranie statusu eksportu paczki faktur |
| [**apiV2InvoicesKsefKsefNumberGet()**](PobieranieFakturApi.md#apiV2InvoicesKsefKsefNumberGet) | **GET** /api/v2/invoices/ksef/{ksefNumber} | Pobranie faktury po numerze KSeF |
| [**apiV2InvoicesQueryMetadataPost()**](PobieranieFakturApi.md#apiV2InvoicesQueryMetadataPost) | **POST** /api/v2/invoices/query/metadata | Pobranie listy metadanych faktur |


## `apiV2InvoicesExportsPost()`

```php
apiV2InvoicesExportsPost($invoice_export_request): \NetSeven\KseF2Model\ExportInvoicesResponse
```

Eksport paczki faktur

Rozpoczyna asynchroniczny proces wyszukiwania faktur w systemie KSeF na podstawie przekazanych filtrów oraz przygotowania ich w formie zaszyfrowanej paczki. Wymagane jest przekazanie informacji o szyfrowaniu w polu <b>Encryption</b>, które służą do zabezpieczenia przygotowanej paczki z fakturami. Maksymalnie można uruchomić 10 równoczesnych eksportów w zalogowanym kontekście.              System pobiera faktury rosnąco według daty określonej w filtrze (Invoicing, Issue, PermanentStorage) i dodaje faktury(nazwa pliku: <b>{ksefNumber}.xml</b>) do paczki aż do osiągnięcia jednego z poniższych limitów: * Limit liczby faktur: 10 000 sztuk * Limit rozmiaru danych(skompresowanych): 1GB  Paczka eksportu zawiera dodatkowy plik z metadanymi faktur w formacie JSON (`_metadata.json`). Zawartość pliku to obiekt z tablicą <b>invoices</b>, gdzie każdy element jest obiektem typu <b>InvoiceMetadata</b> (taki jak zwracany przez endpoint `POST /invoices/query/metadata`).  <b>Plik z metadanymi(_metadata.json) nie jest wliczany do limitów algorytmu budowania paczki</b>.   `Do realizacji pobierania przyrostowego należy stosować filtrowanie po dacie PermanentStorage`.  **Sortowanie:**  - permanentStorageDate | invoicingDate | issueDate (Asc) - pole wybierane na podstawie filtrów    **Wymagane uprawnienia**: `InvoiceRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\PobieranieFakturApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$invoice_export_request = {"encryption":{"encryptedSymmetricKey":"Rk1Qb1VhVjMyQ3NxQ1h1WlVtZUdHcDJSZ0pTbE5IbWQ=","initializationVector":"c29tZUluaXRWZWN0b3I="},"filters":{"subjectType":"Subject1","dateRange":{"dateType":"Issue","from":"2025-08-28T09:22:13.388+00:00","to":"2025-09-28T09:22:13.388+00:00"}}}; // \NetSeven\KseF2Model\InvoiceExportRequest | Dane wejściowe określające kryteria i format eksportu paczki faktur.

try {
    $result = $apiInstance->apiV2InvoicesExportsPost($invoice_export_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PobieranieFakturApi->apiV2InvoicesExportsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **invoice_export_request** | [**\NetSeven\KseF2Model\InvoiceExportRequest**](../Model/InvoiceExportRequest.md)| Dane wejściowe określające kryteria i format eksportu paczki faktur. | [optional] |

### Return type

[**\NetSeven\KseF2Model\ExportInvoicesResponse**](../Model/ExportInvoicesResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2InvoicesExportsReferenceNumberGet()`

```php
apiV2InvoicesExportsReferenceNumberGet($reference_number): \NetSeven\KseF2Model\InvoiceExportStatusResponse
```

Pobranie statusu eksportu paczki faktur

Paczka faktur jest dzielona na części o maksymalnym rozmiarze 50 MB. Każda część jest zaszyfrowana algorytmem AES-256-CBC z dopełnieniem PKCS#7, przy użyciu klucza symetrycznego przekazanego podczas inicjowania eksportu.   W przypadku ucięcia wyniku eksportu z powodu przekroczenia limitów, zwracana jest flaga <b>IsTruncated = true</b> oraz odpowiednia data, którą należy wykorzystać do wykonania kolejnego eksportu, aż do momentu, gdy flaga <b>IsTruncated = false</b>.  **Sortowanie:**  - permanentStorageDate | invoicingDate | issueDate (Asc) - pole wybierane na podstawie filtrów    **Wymagane uprawnienia**: `InvoiceRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\PobieranieFakturApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$reference_number = 'reference_number_example'; // string | Numer referencyjny eksportu faktur.

try {
    $result = $apiInstance->apiV2InvoicesExportsReferenceNumberGet($reference_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PobieranieFakturApi->apiV2InvoicesExportsReferenceNumberGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reference_number** | **string**| Numer referencyjny eksportu faktur. | |

### Return type

[**\NetSeven\KseF2Model\InvoiceExportStatusResponse**](../Model/InvoiceExportStatusResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2InvoicesKsefKsefNumberGet()`

```php
apiV2InvoicesKsefKsefNumberGet($ksef_number): string
```

Pobranie faktury po numerze KSeF

Zwraca fakturę o podanym numerze KSeF.  **Wymagane uprawnienia**: `InvoiceRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\PobieranieFakturApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ksef_number = 'ksef_number_example'; // string | Numer KSeF faktury.

try {
    $result = $apiInstance->apiV2InvoicesKsefKsefNumberGet($ksef_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PobieranieFakturApi->apiV2InvoicesKsefKsefNumberGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ksef_number** | **string**| Numer KSeF faktury. | |

### Return type

**string**

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/xml`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV2InvoicesQueryMetadataPost()`

```php
apiV2InvoicesQueryMetadataPost($sort_order, $page_offset, $page_size, $invoice_query_filters): \NetSeven\KseF2Model\QueryInvoicesMetadataResponse
```

Pobranie listy metadanych faktur

Zwraca metadane faktur spełniających filtry.  Limit techniczny: ≤ 10 000 rekordów na zestaw filtrów, po jego osiągnięciu <b>isTruncated = true</b> i należy ponownie ustawić <b>dateRange</b>, używając ostatniej daty z wyników (tj. ustawić from/to - w zależności od kierunku sortowania, od daty ostatniego zwróconego rekordu) oraz wyzerować <b>pageOffset</b>.  `Do scenariusza przyrostowego należy używać daty PermanentStorage oraz kolejność sortowania Asc`.              <b>Scenariusz pobierania przyrostowego (skrót):</b> * Gdy <b>hasMore = false</b>, należy zakończyć, * Gdy <b>hasMore = true</b> i <b>isTruncated = false</b>, należy zwiększyć <b>pageOffset</b>, * Gdy <b>hasMore = true</b> i <b>isTruncated = true</b>, należy zawęzić <b>dateRange</b> (ustawić from od daty ostatniego rekordu), wyzerować <b>pageOffset</b> i kontynuować  **Sortowanie:**  - permanentStorageDate | invoicingDate | issueDate (Asc | Desc) - pole wybierane na podstawie filtrów    **Wymagane uprawnienia**: `InvoiceRead`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: Bearer
$config = NetSeven\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new NetSeven\Api\PobieranieFakturApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$sort_order = new \NetSeven\KseF2Model\\NetSevenKseF2ModelSortOrder(); // \NetSevenKseF2ModelSortOrder | Kolejność sortowania wyników. | Wartość | Opis | | --- | --- | | Asc | Sortowanie rosnąco. | | Desc | Sortowanie malejąco. |
$page_offset = 0; // int | Indeks pierwszej strony wyników (0 = pierwsza strona).
$page_size = 10; // int | Rozmiar strony wyników.
$invoice_query_filters = {"subjectType":"Subject1","dateRange":{"dateType":"PermanentStorage","from":"2025-08-28T09:22:13.388+00:00","to":"2025-09-28T09:22:13.388+00:00"},"amount":{"type":"Brutto","from":100.5,"to":250.0},"currencyCodes":["PLN","EUR"],"invoicingMode":"Online","formType":"FA","invoiceTypes":["Vat"],"hasAttachment":true}; // \NetSeven\KseF2Model\InvoiceQueryFilters | Kryteria filtrowania.

try {
    $result = $apiInstance->apiV2InvoicesQueryMetadataPost($sort_order, $page_offset, $page_size, $invoice_query_filters);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PobieranieFakturApi->apiV2InvoicesQueryMetadataPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **sort_order** | [**\NetSevenKseF2ModelSortOrder**](../Model/.md)| Kolejność sortowania wyników. | Wartość | Opis | | --- | --- | | Asc | Sortowanie rosnąco. | | Desc | Sortowanie malejąco. | | [optional] |
| **page_offset** | **int**| Indeks pierwszej strony wyników (0 &#x3D; pierwsza strona). | [optional] [default to 0] |
| **page_size** | **int**| Rozmiar strony wyników. | [optional] [default to 10] |
| **invoice_query_filters** | [**\NetSeven\KseF2Model\InvoiceQueryFilters**](../Model/InvoiceQueryFilters.md)| Kryteria filtrowania. | [optional] |

### Return type

[**\NetSeven\KseF2Model\QueryInvoicesMetadataResponse**](../Model/QueryInvoicesMetadataResponse.md)

### Authorization

[Bearer](../../README.md#Bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
