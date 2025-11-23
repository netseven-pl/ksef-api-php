# ksef-api-php

**Wersja API:** 2.0.0 (build 2.0.0-rc5.7-te-20251115.1+12de7e512c6dede0af882fee4f7e52fc04590ab4)<br>
**Klucze publiczne** Ministerstwa Finansów (dla danego środowiska): [Pobierz klucze](#tag/Certyfikaty-klucza-publicznego)<br>
**Historia zmian:** [Changelog](https://github.com/CIRFMF/ksef-docs/blob/main/api-changelog.md)<br>
**Rozszerzona dokumentacja API:** [ksef-docs](https://github.com/CIRFMF/ksef-docs/tree/main)



## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/ksef-api-php/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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

## API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AktywneSesjeApi* | [**apiV2AuthSessionsCurrentDelete**](docs/Api/AktywneSesjeApi.md#apiv2authsessionscurrentdelete) | **DELETE** /api/v2/auth/sessions/current | Unieważnienie aktualnej sesji uwierzytelnienia
*AktywneSesjeApi* | [**apiV2AuthSessionsGet**](docs/Api/AktywneSesjeApi.md#apiv2authsessionsget) | **GET** /api/v2/auth/sessions | Pobranie listy aktywnych sesji
*AktywneSesjeApi* | [**apiV2AuthSessionsReferenceNumberDelete**](docs/Api/AktywneSesjeApi.md#apiv2authsessionsreferencenumberdelete) | **DELETE** /api/v2/auth/sessions/{referenceNumber} | Unieważnienie sesji uwierzytelnienia
*CertyfikatyApi* | [**apiV2CertificatesCertificateSerialNumberRevokePost**](docs/Api/CertyfikatyApi.md#apiv2certificatescertificateserialnumberrevokepost) | **POST** /api/v2/certificates/{certificateSerialNumber}/revoke | Unieważnienie certyfikatu
*CertyfikatyApi* | [**apiV2CertificatesEnrollmentsDataGet**](docs/Api/CertyfikatyApi.md#apiv2certificatesenrollmentsdataget) | **GET** /api/v2/certificates/enrollments/data | Pobranie danych do wniosku certyfikacyjnego
*CertyfikatyApi* | [**apiV2CertificatesEnrollmentsPost**](docs/Api/CertyfikatyApi.md#apiv2certificatesenrollmentspost) | **POST** /api/v2/certificates/enrollments | Wysyłka wniosku certyfikacyjnego
*CertyfikatyApi* | [**apiV2CertificatesEnrollmentsReferenceNumberGet**](docs/Api/CertyfikatyApi.md#apiv2certificatesenrollmentsreferencenumberget) | **GET** /api/v2/certificates/enrollments/{referenceNumber} | Pobranie statusu przetwarzania wniosku certyfikacyjnego
*CertyfikatyApi* | [**apiV2CertificatesLimitsGet**](docs/Api/CertyfikatyApi.md#apiv2certificateslimitsget) | **GET** /api/v2/certificates/limits | Pobranie danych o limitach certyfikatów
*CertyfikatyApi* | [**apiV2CertificatesQueryPost**](docs/Api/CertyfikatyApi.md#apiv2certificatesquerypost) | **POST** /api/v2/certificates/query | Pobranie listy metadanych certyfikatów
*CertyfikatyApi* | [**apiV2CertificatesRetrievePost**](docs/Api/CertyfikatyApi.md#apiv2certificatesretrievepost) | **POST** /api/v2/certificates/retrieve | Pobranie certyfikatu lub listy certyfikatów
*CertyfikatyKluczaPublicznegoApi* | [**apiV2SecurityPublicKeyCertificatesGet**](docs/Api/CertyfikatyKluczaPublicznegoApi.md#apiv2securitypublickeycertificatesget) | **GET** /api/v2/security/public-key-certificates | Pobranie certyfikatów
*DaneTestoweApi* | [**apiV2TestdataAttachmentPost**](docs/Api/DaneTestoweApi.md#apiv2testdataattachmentpost) | **POST** /api/v2/testdata/attachment | Umożliwienie wysyłania faktur z załącznikiem
*DaneTestoweApi* | [**apiV2TestdataAttachmentRevokePost**](docs/Api/DaneTestoweApi.md#apiv2testdataattachmentrevokepost) | **POST** /api/v2/testdata/attachment/revoke | Odebranie możliwości wysyłania faktur z załącznikiem
*DaneTestoweApi* | [**apiV2TestdataPermissionsPost**](docs/Api/DaneTestoweApi.md#apiv2testdatapermissionspost) | **POST** /api/v2/testdata/permissions | Nadanie uprawnień testowemu podmiotowi/osobie fizycznej
*DaneTestoweApi* | [**apiV2TestdataPermissionsRevokePost**](docs/Api/DaneTestoweApi.md#apiv2testdatapermissionsrevokepost) | **POST** /api/v2/testdata/permissions/revoke | Odebranie uprawnień testowemu podmiotowi/osobie fizycznej
*DaneTestoweApi* | [**apiV2TestdataPersonPost**](docs/Api/DaneTestoweApi.md#apiv2testdatapersonpost) | **POST** /api/v2/testdata/person | Utworzenie osoby fizycznej
*DaneTestoweApi* | [**apiV2TestdataPersonRemovePost**](docs/Api/DaneTestoweApi.md#apiv2testdatapersonremovepost) | **POST** /api/v2/testdata/person/remove | Usunięcie osoby fizycznej
*DaneTestoweApi* | [**apiV2TestdataSubjectPost**](docs/Api/DaneTestoweApi.md#apiv2testdatasubjectpost) | **POST** /api/v2/testdata/subject | Utworzenie podmiotu
*DaneTestoweApi* | [**apiV2TestdataSubjectRemovePost**](docs/Api/DaneTestoweApi.md#apiv2testdatasubjectremovepost) | **POST** /api/v2/testdata/subject/remove | Usunięcie podmiotu
*LimityIOgraniczeniaApi* | [**apiV2LimitsContextGet**](docs/Api/LimityIOgraniczeniaApi.md#apiv2limitscontextget) | **GET** /api/v2/limits/context | Pobranie limitów dla bieżącego kontekstu
*LimityIOgraniczeniaApi* | [**apiV2LimitsSubjectGet**](docs/Api/LimityIOgraniczeniaApi.md#apiv2limitssubjectget) | **GET** /api/v2/limits/subject | Pobranie limitów dla bieżącego podmiotu
*LimityIOgraniczeniaApi* | [**apiV2RateLimitsGet**](docs/Api/LimityIOgraniczeniaApi.md#apiv2ratelimitsget) | **GET** /api/v2/rate-limits | Pobranie aktualnie obowiązujących limitów API
*LimityIOgraniczeniaApi* | [**apiV2TestdataLimitsContextSessionDelete**](docs/Api/LimityIOgraniczeniaApi.md#apiv2testdatalimitscontextsessiondelete) | **DELETE** /api/v2/testdata/limits/context/session | Przywrócenie domyślnych wartości limitów sesji dla bieżącego kontekstu
*LimityIOgraniczeniaApi* | [**apiV2TestdataLimitsContextSessionPost**](docs/Api/LimityIOgraniczeniaApi.md#apiv2testdatalimitscontextsessionpost) | **POST** /api/v2/testdata/limits/context/session | Zmiana limitów sesji dla bieżącego kontekstu
*LimityIOgraniczeniaApi* | [**apiV2TestdataLimitsSubjectCertificateDelete**](docs/Api/LimityIOgraniczeniaApi.md#apiv2testdatalimitssubjectcertificatedelete) | **DELETE** /api/v2/testdata/limits/subject/certificate | Przywrócenie domyślnych wartości limitów certyfikatów dla bieżącego podmiotu
*LimityIOgraniczeniaApi* | [**apiV2TestdataLimitsSubjectCertificatePost**](docs/Api/LimityIOgraniczeniaApi.md#apiv2testdatalimitssubjectcertificatepost) | **POST** /api/v2/testdata/limits/subject/certificate | Zmiana limitów certyfikatów dla bieżącego podmiotu
*LimityIOgraniczeniaApi* | [**apiV2TestdataRateLimitsDelete**](docs/Api/LimityIOgraniczeniaApi.md#apiv2testdataratelimitsdelete) | **DELETE** /api/v2/testdata/rate-limits | Przywrócenie domyślnych wartości limitów API dla bieżącego kontekstu
*LimityIOgraniczeniaApi* | [**apiV2TestdataRateLimitsPost**](docs/Api/LimityIOgraniczeniaApi.md#apiv2testdataratelimitspost) | **POST** /api/v2/testdata/rate-limits | Zmiana limitów API dla bieżącego kontekstu
*NadawanieUprawnieApi* | [**apiV2PermissionsAuthorizationsGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionsauthorizationsgrantspost) | **POST** /api/v2/permissions/authorizations/grants | Nadanie uprawnień podmiotowych
*NadawanieUprawnieApi* | [**apiV2PermissionsEntitiesGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionsentitiesgrantspost) | **POST** /api/v2/permissions/entities/grants | Nadanie podmiotom uprawnień do obsługi faktur
*NadawanieUprawnieApi* | [**apiV2PermissionsEuEntitiesAdministrationGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionseuentitiesadministrationgrantspost) | **POST** /api/v2/permissions/eu-entities/administration/grants | Nadanie uprawnień administratora podmiotu unijnego
*NadawanieUprawnieApi* | [**apiV2PermissionsEuEntitiesGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionseuentitiesgrantspost) | **POST** /api/v2/permissions/eu-entities/grants | Nadanie uprawnień reprezentanta podmiotu unijnego
*NadawanieUprawnieApi* | [**apiV2PermissionsIndirectGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionsindirectgrantspost) | **POST** /api/v2/permissions/indirect/grants | Nadanie uprawnień w sposób pośredni
*NadawanieUprawnieApi* | [**apiV2PermissionsPersonsGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionspersonsgrantspost) | **POST** /api/v2/permissions/persons/grants | Nadanie osobom fizycznym uprawnień do pracy w KSeF
*NadawanieUprawnieApi* | [**apiV2PermissionsSubunitsGrantsPost**](docs/Api/NadawanieUprawnieApi.md#apiv2permissionssubunitsgrantspost) | **POST** /api/v2/permissions/subunits/grants | Nadanie uprawnień administratora podmiotu podrzędnego
*OdbieranieUprawnieApi* | [**apiV2PermissionsAuthorizationsGrantsPermissionIdDelete**](docs/Api/OdbieranieUprawnieApi.md#apiv2permissionsauthorizationsgrantspermissioniddelete) | **DELETE** /api/v2/permissions/authorizations/grants/{permissionId} | Odebranie uprawnień podmiotowych
*OdbieranieUprawnieApi* | [**apiV2PermissionsCommonGrantsPermissionIdDelete**](docs/Api/OdbieranieUprawnieApi.md#apiv2permissionscommongrantspermissioniddelete) | **DELETE** /api/v2/permissions/common/grants/{permissionId} | Odebranie uprawnień
*OperacjeApi* | [**apiV2PermissionsAttachmentsStatusGet**](docs/Api/OperacjeApi.md#apiv2permissionsattachmentsstatusget) | **GET** /api/v2/permissions/attachments/status | Sprawdzenie statusu zgody na wystawianie faktur z załącznikiem
*OperacjeApi* | [**apiV2PermissionsOperationsReferenceNumberGet**](docs/Api/OperacjeApi.md#apiv2permissionsoperationsreferencenumberget) | **GET** /api/v2/permissions/operations/{referenceNumber} | Pobranie statusu operacji
*PobieranieFakturApi* | [**apiV2InvoicesExportsPost**](docs/Api/PobieranieFakturApi.md#apiv2invoicesexportspost) | **POST** /api/v2/invoices/exports | Eksport paczki faktur
*PobieranieFakturApi* | [**apiV2InvoicesExportsReferenceNumberGet**](docs/Api/PobieranieFakturApi.md#apiv2invoicesexportsreferencenumberget) | **GET** /api/v2/invoices/exports/{referenceNumber} | Pobranie statusu eksportu paczki faktur
*PobieranieFakturApi* | [**apiV2InvoicesKsefKsefNumberGet**](docs/Api/PobieranieFakturApi.md#apiv2invoicesksefksefnumberget) | **GET** /api/v2/invoices/ksef/{ksefNumber} | Pobranie faktury po numerze KSeF
*PobieranieFakturApi* | [**apiV2InvoicesQueryMetadataPost**](docs/Api/PobieranieFakturApi.md#apiv2invoicesquerymetadatapost) | **POST** /api/v2/invoices/query/metadata | Pobranie listy metadanych faktur
*StatusWysykiIUPOApi* | [**apiV2SessionsGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsget) | **GET** /api/v2/sessions | Pobranie listy sesji
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberget) | **GET** /api/v2/sessions/{referenceNumber} | Pobranie statusu sesji
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberInvoicesFailedGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberinvoicesfailedget) | **GET** /api/v2/sessions/{referenceNumber}/invoices/failed | Pobranie niepoprawnie przetworzonych faktur sesji
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberInvoicesGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberinvoicesget) | **GET** /api/v2/sessions/{referenceNumber}/invoices | Pobranie faktur sesji
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberInvoicesInvoiceReferenceNumberGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberinvoicesinvoicereferencenumberget) | **GET** /api/v2/sessions/{referenceNumber}/invoices/{invoiceReferenceNumber} | Pobranie statusu faktury z sesji
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberInvoicesInvoiceReferenceNumberUpoGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberinvoicesinvoicereferencenumberupoget) | **GET** /api/v2/sessions/{referenceNumber}/invoices/{invoiceReferenceNumber}/upo | Pobranie UPO faktury z sesji na podstawie numeru referencyjnego faktury
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberInvoicesKsefKsefNumberUpoGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberinvoicesksefksefnumberupoget) | **GET** /api/v2/sessions/{referenceNumber}/invoices/ksef/{ksefNumber}/upo | Pobranie UPO faktury z sesji na podstawie numeru KSeF
*StatusWysykiIUPOApi* | [**apiV2SessionsReferenceNumberUpoUpoReferenceNumberGet**](docs/Api/StatusWysykiIUPOApi.md#apiv2sessionsreferencenumberupouporeferencenumberget) | **GET** /api/v2/sessions/{referenceNumber}/upo/{upoReferenceNumber} | Pobranie UPO dla sesji
*TokenyKSeFApi* | [**apiV2TokensGet**](docs/Api/TokenyKSeFApi.md#apiv2tokensget) | **GET** /api/v2/tokens | Pobranie listy wygenerowanych tokenów
*TokenyKSeFApi* | [**apiV2TokensPost**](docs/Api/TokenyKSeFApi.md#apiv2tokenspost) | **POST** /api/v2/tokens | Wygenerowanie nowego tokena
*TokenyKSeFApi* | [**apiV2TokensReferenceNumberDelete**](docs/Api/TokenyKSeFApi.md#apiv2tokensreferencenumberdelete) | **DELETE** /api/v2/tokens/{referenceNumber} | Unieważnienie tokena
*TokenyKSeFApi* | [**apiV2TokensReferenceNumberGet**](docs/Api/TokenyKSeFApi.md#apiv2tokensreferencenumberget) | **GET** /api/v2/tokens/{referenceNumber} | Pobranie statusu tokena
*UsugiPeppolApi* | [**apiV2PeppolQueryGet**](docs/Api/UsugiPeppolApi.md#apiv2peppolqueryget) | **GET** /api/v2/peppol/query | Pobranie listy dostawców usług Peppol
*UzyskiwanieDostpuApi* | [**apiV2AuthChallengePost**](docs/Api/UzyskiwanieDostpuApi.md#apiv2authchallengepost) | **POST** /api/v2/auth/challenge | Inicjalizacja uwierzytelnienia
*UzyskiwanieDostpuApi* | [**apiV2AuthKsefTokenPost**](docs/Api/UzyskiwanieDostpuApi.md#apiv2authkseftokenpost) | **POST** /api/v2/auth/ksef-token | Uwierzytelnienie z wykorzystaniem tokena KSeF
*UzyskiwanieDostpuApi* | [**apiV2AuthReferenceNumberGet**](docs/Api/UzyskiwanieDostpuApi.md#apiv2authreferencenumberget) | **GET** /api/v2/auth/{referenceNumber} | Pobranie statusu uwierzytelniania
*UzyskiwanieDostpuApi* | [**apiV2AuthTokenRedeemPost**](docs/Api/UzyskiwanieDostpuApi.md#apiv2authtokenredeempost) | **POST** /api/v2/auth/token/redeem | Pobranie tokenów dostępowych
*UzyskiwanieDostpuApi* | [**apiV2AuthTokenRefreshPost**](docs/Api/UzyskiwanieDostpuApi.md#apiv2authtokenrefreshpost) | **POST** /api/v2/auth/token/refresh | Odświeżenie tokena dostępowego
*UzyskiwanieDostpuApi* | [**apiV2AuthXadesSignaturePost**](docs/Api/UzyskiwanieDostpuApi.md#apiv2authxadessignaturepost) | **POST** /api/v2/auth/xades-signature | Uwierzytelnienie z wykorzystaniem podpisu XAdES
*WysykaInteraktywnaApi* | [**apiV2SessionsOnlinePost**](docs/Api/WysykaInteraktywnaApi.md#apiv2sessionsonlinepost) | **POST** /api/v2/sessions/online | Otwarcie sesji interaktywnej
*WysykaInteraktywnaApi* | [**apiV2SessionsOnlineReferenceNumberClosePost**](docs/Api/WysykaInteraktywnaApi.md#apiv2sessionsonlinereferencenumberclosepost) | **POST** /api/v2/sessions/online/{referenceNumber}/close | Zamknięcie sesji interaktywnej
*WysykaInteraktywnaApi* | [**apiV2SessionsOnlineReferenceNumberInvoicesPost**](docs/Api/WysykaInteraktywnaApi.md#apiv2sessionsonlinereferencenumberinvoicespost) | **POST** /api/v2/sessions/online/{referenceNumber}/invoices | Wysłanie faktury
*WysykaWsadowaApi* | [**apiV2SessionsBatchPost**](docs/Api/WysykaWsadowaApi.md#apiv2sessionsbatchpost) | **POST** /api/v2/sessions/batch | Otwarcie sesji wsadowej
*WysykaWsadowaApi* | [**apiV2SessionsBatchReferenceNumberClosePost**](docs/Api/WysykaWsadowaApi.md#apiv2sessionsbatchreferencenumberclosepost) | **POST** /api/v2/sessions/batch/{referenceNumber}/close | Zamknięcie sesji wsadowej
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQueryAuthorizationsGrantsPost**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsqueryauthorizationsgrantspost) | **POST** /api/v2/permissions/query/authorizations/grants | Pobranie listy uprawnień podmiotowych do obsługi faktur
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQueryEntitiesRolesGet**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsqueryentitiesrolesget) | **GET** /api/v2/permissions/query/entities/roles | Pobranie listy ról podmiotu
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQueryEuEntitiesGrantsPost**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsqueryeuentitiesgrantspost) | **POST** /api/v2/permissions/query/eu-entities/grants | Pobranie listy uprawnień administratorów lub reprezentantów podmiotów unijnych uprawnionych do samofakturowania
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQueryPersonalGrantsPost**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsquerypersonalgrantspost) | **POST** /api/v2/permissions/query/personal/grants | Pobranie listy własnych uprawnień
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQueryPersonsGrantsPost**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsquerypersonsgrantspost) | **POST** /api/v2/permissions/query/persons/grants | Pobranie listy uprawnień do pracy w KSeF nadanych osobom fizycznym lub podmiotom
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQuerySubordinateEntitiesRolesPost**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsquerysubordinateentitiesrolespost) | **POST** /api/v2/permissions/query/subordinate-entities/roles | Pobranie listy podmiotów podrzędnych
*WyszukiwanieNadanychUprawnieApi* | [**apiV2PermissionsQuerySubunitsGrantsPost**](docs/Api/WyszukiwanieNadanychUprawnieApi.md#apiv2permissionsquerysubunitsgrantspost) | **POST** /api/v2/permissions/query/subunits/grants | Pobranie listy uprawnień administratorów jednostek i podmiotów podrzędnych

## Models

- [AllowedIps](docs/Model/AllowedIps.md)
- [AmountType](docs/Model/AmountType.md)
- [ApiRateLimitValuesOverride](docs/Model/ApiRateLimitValuesOverride.md)
- [ApiRateLimitsOverride](docs/Model/ApiRateLimitsOverride.md)
- [AttachmentPermissionGrantRequest](docs/Model/AttachmentPermissionGrantRequest.md)
- [AttachmentPermissionRevokeRequest](docs/Model/AttachmentPermissionRevokeRequest.md)
- [AuthenticationChallengeResponse](docs/Model/AuthenticationChallengeResponse.md)
- [AuthenticationContextIdentifier](docs/Model/AuthenticationContextIdentifier.md)
- [AuthenticationContextIdentifierType](docs/Model/AuthenticationContextIdentifierType.md)
- [AuthenticationInitResponse](docs/Model/AuthenticationInitResponse.md)
- [AuthenticationListItem](docs/Model/AuthenticationListItem.md)
- [AuthenticationListResponse](docs/Model/AuthenticationListResponse.md)
- [AuthenticationMethod](docs/Model/AuthenticationMethod.md)
- [AuthenticationOperationStatusResponse](docs/Model/AuthenticationOperationStatusResponse.md)
- [AuthenticationTokenRefreshResponse](docs/Model/AuthenticationTokenRefreshResponse.md)
- [AuthenticationTokenStatus](docs/Model/AuthenticationTokenStatus.md)
- [AuthenticationTokensResponse](docs/Model/AuthenticationTokensResponse.md)
- [AuthorizationPolicy](docs/Model/AuthorizationPolicy.md)
- [BatchFileInfo](docs/Model/BatchFileInfo.md)
- [BatchFilePartInfo](docs/Model/BatchFilePartInfo.md)
- [BatchSessionContextLimitsOverride](docs/Model/BatchSessionContextLimitsOverride.md)
- [BatchSessionEffectiveContextLimits](docs/Model/BatchSessionEffectiveContextLimits.md)
- [BuyerIdentifierType](docs/Model/BuyerIdentifierType.md)
- [CertificateEffectiveSubjectLimits](docs/Model/CertificateEffectiveSubjectLimits.md)
- [CertificateEnrollmentDataResponse](docs/Model/CertificateEnrollmentDataResponse.md)
- [CertificateEnrollmentStatusResponse](docs/Model/CertificateEnrollmentStatusResponse.md)
- [CertificateLimit](docs/Model/CertificateLimit.md)
- [CertificateLimitsResponse](docs/Model/CertificateLimitsResponse.md)
- [CertificateListItem](docs/Model/CertificateListItem.md)
- [CertificateListItemStatus](docs/Model/CertificateListItemStatus.md)
- [CertificateRevocationReason](docs/Model/CertificateRevocationReason.md)
- [CertificateSubjectIdentifier](docs/Model/CertificateSubjectIdentifier.md)
- [CertificateSubjectIdentifierType](docs/Model/CertificateSubjectIdentifierType.md)
- [CertificateSubjectLimitsOverride](docs/Model/CertificateSubjectLimitsOverride.md)
- [CheckAttachmentPermissionStatusResponse](docs/Model/CheckAttachmentPermissionStatusResponse.md)
- [CommonSessionStatus](docs/Model/CommonSessionStatus.md)
- [CurrencyCode](docs/Model/CurrencyCode.md)
- [EffectiveApiRateLimitValues](docs/Model/EffectiveApiRateLimitValues.md)
- [EffectiveApiRateLimits](docs/Model/EffectiveApiRateLimits.md)
- [EffectiveContextLimits](docs/Model/EffectiveContextLimits.md)
- [EffectiveSubjectLimits](docs/Model/EffectiveSubjectLimits.md)
- [EncryptionInfo](docs/Model/EncryptionInfo.md)
- [EnrollCertificateRequest](docs/Model/EnrollCertificateRequest.md)
- [EnrollCertificateResponse](docs/Model/EnrollCertificateResponse.md)
- [EnrollmentEffectiveSubjectLimits](docs/Model/EnrollmentEffectiveSubjectLimits.md)
- [EnrollmentSubjectLimitsOverride](docs/Model/EnrollmentSubjectLimitsOverride.md)
- [EntityAuthorizationGrant](docs/Model/EntityAuthorizationGrant.md)
- [EntityAuthorizationPermissionType](docs/Model/EntityAuthorizationPermissionType.md)
- [EntityAuthorizationPermissionsGrantRequest](docs/Model/EntityAuthorizationPermissionsGrantRequest.md)
- [EntityAuthorizationPermissionsQueryRequest](docs/Model/EntityAuthorizationPermissionsQueryRequest.md)
- [EntityAuthorizationPermissionsSubjectIdentifier](docs/Model/EntityAuthorizationPermissionsSubjectIdentifier.md)
- [EntityAuthorizationPermissionsSubjectIdentifierType](docs/Model/EntityAuthorizationPermissionsSubjectIdentifierType.md)
- [EntityAuthorizationsAuthorIdentifier](docs/Model/EntityAuthorizationsAuthorIdentifier.md)
- [EntityAuthorizationsAuthorIdentifierType](docs/Model/EntityAuthorizationsAuthorIdentifierType.md)
- [EntityAuthorizationsAuthorizedEntityIdentifier](docs/Model/EntityAuthorizationsAuthorizedEntityIdentifier.md)
- [EntityAuthorizationsAuthorizedEntityIdentifierType](docs/Model/EntityAuthorizationsAuthorizedEntityIdentifierType.md)
- [EntityAuthorizationsAuthorizingEntityIdentifier](docs/Model/EntityAuthorizationsAuthorizingEntityIdentifier.md)
- [EntityAuthorizationsAuthorizingEntityIdentifierType](docs/Model/EntityAuthorizationsAuthorizingEntityIdentifierType.md)
- [EntityPermission](docs/Model/EntityPermission.md)
- [EntityPermissionType](docs/Model/EntityPermissionType.md)
- [EntityPermissionsGrantRequest](docs/Model/EntityPermissionsGrantRequest.md)
- [EntityPermissionsSubjectIdentifier](docs/Model/EntityPermissionsSubjectIdentifier.md)
- [EntityPermissionsSubjectIdentifierType](docs/Model/EntityPermissionsSubjectIdentifierType.md)
- [EntityPermissionsSubordinateEntityIdentifier](docs/Model/EntityPermissionsSubordinateEntityIdentifier.md)
- [EntityPermissionsSubordinateEntityIdentifierType](docs/Model/EntityPermissionsSubordinateEntityIdentifierType.md)
- [EntityRole](docs/Model/EntityRole.md)
- [EntityRoleType](docs/Model/EntityRoleType.md)
- [EntityRolesParentEntityIdentifier](docs/Model/EntityRolesParentEntityIdentifier.md)
- [EntityRolesParentEntityIdentifierType](docs/Model/EntityRolesParentEntityIdentifierType.md)
- [EuEntityAdministrationPermissionsContextIdentifier](docs/Model/EuEntityAdministrationPermissionsContextIdentifier.md)
- [EuEntityAdministrationPermissionsContextIdentifierType](docs/Model/EuEntityAdministrationPermissionsContextIdentifierType.md)
- [EuEntityAdministrationPermissionsGrantRequest](docs/Model/EuEntityAdministrationPermissionsGrantRequest.md)
- [EuEntityAdministrationPermissionsSubjectIdentifier](docs/Model/EuEntityAdministrationPermissionsSubjectIdentifier.md)
- [EuEntityAdministrationPermissionsSubjectIdentifierType](docs/Model/EuEntityAdministrationPermissionsSubjectIdentifierType.md)
- [EuEntityPermission](docs/Model/EuEntityPermission.md)
- [EuEntityPermissionType](docs/Model/EuEntityPermissionType.md)
- [EuEntityPermissionsAuthorIdentifier](docs/Model/EuEntityPermissionsAuthorIdentifier.md)
- [EuEntityPermissionsAuthorIdentifierType](docs/Model/EuEntityPermissionsAuthorIdentifierType.md)
- [EuEntityPermissionsGrantRequest](docs/Model/EuEntityPermissionsGrantRequest.md)
- [EuEntityPermissionsQueryPermissionType](docs/Model/EuEntityPermissionsQueryPermissionType.md)
- [EuEntityPermissionsQueryRequest](docs/Model/EuEntityPermissionsQueryRequest.md)
- [EuEntityPermissionsSubjectIdentifier](docs/Model/EuEntityPermissionsSubjectIdentifier.md)
- [EuEntityPermissionsSubjectIdentifierType](docs/Model/EuEntityPermissionsSubjectIdentifierType.md)
- [ExceptionDetails](docs/Model/ExceptionDetails.md)
- [ExceptionInfo](docs/Model/ExceptionInfo.md)
- [ExceptionResponse](docs/Model/ExceptionResponse.md)
- [ExportInvoicesResponse](docs/Model/ExportInvoicesResponse.md)
- [FormCode](docs/Model/FormCode.md)
- [GenerateTokenRequest](docs/Model/GenerateTokenRequest.md)
- [GenerateTokenResponse](docs/Model/GenerateTokenResponse.md)
- [IndirectPermissionType](docs/Model/IndirectPermissionType.md)
- [IndirectPermissionsGrantRequest](docs/Model/IndirectPermissionsGrantRequest.md)
- [IndirectPermissionsSubjectIdentifier](docs/Model/IndirectPermissionsSubjectIdentifier.md)
- [IndirectPermissionsSubjectIdentifierType](docs/Model/IndirectPermissionsSubjectIdentifierType.md)
- [IndirectPermissionsTargetIdentifier](docs/Model/IndirectPermissionsTargetIdentifier.md)
- [IndirectPermissionsTargetIdentifierType](docs/Model/IndirectPermissionsTargetIdentifierType.md)
- [InitTokenAuthenticationRequest](docs/Model/InitTokenAuthenticationRequest.md)
- [InvoiceExportRequest](docs/Model/InvoiceExportRequest.md)
- [InvoiceExportStatusResponse](docs/Model/InvoiceExportStatusResponse.md)
- [InvoiceMetadata](docs/Model/InvoiceMetadata.md)
- [InvoiceMetadataAuthorizedSubject](docs/Model/InvoiceMetadataAuthorizedSubject.md)
- [InvoiceMetadataBuyer](docs/Model/InvoiceMetadataBuyer.md)
- [InvoiceMetadataBuyerIdentifier](docs/Model/InvoiceMetadataBuyerIdentifier.md)
- [InvoiceMetadataSeller](docs/Model/InvoiceMetadataSeller.md)
- [InvoiceMetadataThirdSubject](docs/Model/InvoiceMetadataThirdSubject.md)
- [InvoiceMetadataThirdSubjectIdentifier](docs/Model/InvoiceMetadataThirdSubjectIdentifier.md)
- [InvoicePackage](docs/Model/InvoicePackage.md)
- [InvoicePackagePart](docs/Model/InvoicePackagePart.md)
- [InvoicePermissionType](docs/Model/InvoicePermissionType.md)
- [InvoiceQueryAmount](docs/Model/InvoiceQueryAmount.md)
- [InvoiceQueryBuyerIdentifier](docs/Model/InvoiceQueryBuyerIdentifier.md)
- [InvoiceQueryDateRange](docs/Model/InvoiceQueryDateRange.md)
- [InvoiceQueryDateType](docs/Model/InvoiceQueryDateType.md)
- [InvoiceQueryFilters](docs/Model/InvoiceQueryFilters.md)
- [InvoiceQueryFormType](docs/Model/InvoiceQueryFormType.md)
- [InvoiceQuerySubjectType](docs/Model/InvoiceQuerySubjectType.md)
- [InvoiceType](docs/Model/InvoiceType.md)
- [InvoicingMode](docs/Model/InvoicingMode.md)
- [KsefCertificateType](docs/Model/KsefCertificateType.md)
- [OnlineSessionContextLimitsOverride](docs/Model/OnlineSessionContextLimitsOverride.md)
- [OnlineSessionEffectiveContextLimits](docs/Model/OnlineSessionEffectiveContextLimits.md)
- [OpenBatchSessionRequest](docs/Model/OpenBatchSessionRequest.md)
- [OpenBatchSessionResponse](docs/Model/OpenBatchSessionResponse.md)
- [OpenOnlineSessionRequest](docs/Model/OpenOnlineSessionRequest.md)
- [OpenOnlineSessionResponse](docs/Model/OpenOnlineSessionResponse.md)
- [PartUploadRequest](docs/Model/PartUploadRequest.md)
- [PeppolProvider](docs/Model/PeppolProvider.md)
- [PermissionState](docs/Model/PermissionState.md)
- [PermissionsOperationResponse](docs/Model/PermissionsOperationResponse.md)
- [PermissionsOperationStatusResponse](docs/Model/PermissionsOperationStatusResponse.md)
- [PersonCreateRequest](docs/Model/PersonCreateRequest.md)
- [PersonPermission](docs/Model/PersonPermission.md)
- [PersonPermissionScope](docs/Model/PersonPermissionScope.md)
- [PersonPermissionType](docs/Model/PersonPermissionType.md)
- [PersonPermissionsAuthorIdentifier](docs/Model/PersonPermissionsAuthorIdentifier.md)
- [PersonPermissionsAuthorIdentifierType](docs/Model/PersonPermissionsAuthorIdentifierType.md)
- [PersonPermissionsAuthorizedIdentifier](docs/Model/PersonPermissionsAuthorizedIdentifier.md)
- [PersonPermissionsAuthorizedIdentifierType](docs/Model/PersonPermissionsAuthorizedIdentifierType.md)
- [PersonPermissionsContextIdentifier](docs/Model/PersonPermissionsContextIdentifier.md)
- [PersonPermissionsContextIdentifierType](docs/Model/PersonPermissionsContextIdentifierType.md)
- [PersonPermissionsGrantRequest](docs/Model/PersonPermissionsGrantRequest.md)
- [PersonPermissionsQueryRequest](docs/Model/PersonPermissionsQueryRequest.md)
- [PersonPermissionsQueryType](docs/Model/PersonPermissionsQueryType.md)
- [PersonPermissionsSubjectIdentifier](docs/Model/PersonPermissionsSubjectIdentifier.md)
- [PersonPermissionsSubjectIdentifierType](docs/Model/PersonPermissionsSubjectIdentifierType.md)
- [PersonPermissionsTargetIdentifier](docs/Model/PersonPermissionsTargetIdentifier.md)
- [PersonPermissionsTargetIdentifierType](docs/Model/PersonPermissionsTargetIdentifierType.md)
- [PersonRemoveRequest](docs/Model/PersonRemoveRequest.md)
- [PersonalPermission](docs/Model/PersonalPermission.md)
- [PersonalPermissionScope](docs/Model/PersonalPermissionScope.md)
- [PersonalPermissionType](docs/Model/PersonalPermissionType.md)
- [PersonalPermissionsAuthorizedIdentifier](docs/Model/PersonalPermissionsAuthorizedIdentifier.md)
- [PersonalPermissionsAuthorizedIdentifierType](docs/Model/PersonalPermissionsAuthorizedIdentifierType.md)
- [PersonalPermissionsContextIdentifier](docs/Model/PersonalPermissionsContextIdentifier.md)
- [PersonalPermissionsContextIdentifierType](docs/Model/PersonalPermissionsContextIdentifierType.md)
- [PersonalPermissionsQueryRequest](docs/Model/PersonalPermissionsQueryRequest.md)
- [PersonalPermissionsTargetIdentifier](docs/Model/PersonalPermissionsTargetIdentifier.md)
- [PersonalPermissionsTargetIdentifierType](docs/Model/PersonalPermissionsTargetIdentifierType.md)
- [PublicKeyCertificate](docs/Model/PublicKeyCertificate.md)
- [PublicKeyCertificateUsage](docs/Model/PublicKeyCertificateUsage.md)
- [QueryCertificatesRequest](docs/Model/QueryCertificatesRequest.md)
- [QueryCertificatesResponse](docs/Model/QueryCertificatesResponse.md)
- [QueryEntityAuthorizationPermissionsResponse](docs/Model/QueryEntityAuthorizationPermissionsResponse.md)
- [QueryEntityRolesResponse](docs/Model/QueryEntityRolesResponse.md)
- [QueryEuEntityPermissionsResponse](docs/Model/QueryEuEntityPermissionsResponse.md)
- [QueryInvoicesMetadataResponse](docs/Model/QueryInvoicesMetadataResponse.md)
- [QueryPeppolProvidersResponse](docs/Model/QueryPeppolProvidersResponse.md)
- [QueryPersonPermissionsResponse](docs/Model/QueryPersonPermissionsResponse.md)
- [QueryPersonalPermissionsResponse](docs/Model/QueryPersonalPermissionsResponse.md)
- [QuerySubordinateEntityRolesResponse](docs/Model/QuerySubordinateEntityRolesResponse.md)
- [QuerySubunitPermissionsResponse](docs/Model/QuerySubunitPermissionsResponse.md)
- [QueryTokensResponse](docs/Model/QueryTokensResponse.md)
- [QueryTokensResponseItem](docs/Model/QueryTokensResponseItem.md)
- [QueryType](docs/Model/QueryType.md)
- [RetrieveCertificatesListItem](docs/Model/RetrieveCertificatesListItem.md)
- [RetrieveCertificatesRequest](docs/Model/RetrieveCertificatesRequest.md)
- [RetrieveCertificatesResponse](docs/Model/RetrieveCertificatesResponse.md)
- [RevokeCertificateRequest](docs/Model/RevokeCertificateRequest.md)
- [SendInvoiceRequest](docs/Model/SendInvoiceRequest.md)
- [SendInvoiceResponse](docs/Model/SendInvoiceResponse.md)
- [SessionInvoiceStatusResponse](docs/Model/SessionInvoiceStatusResponse.md)
- [SessionInvoicesResponse](docs/Model/SessionInvoicesResponse.md)
- [SessionStatusResponse](docs/Model/SessionStatusResponse.md)
- [SessionType](docs/Model/SessionType.md)
- [SessionsQueryResponse](docs/Model/SessionsQueryResponse.md)
- [SessionsQueryResponseItem](docs/Model/SessionsQueryResponseItem.md)
- [SetRateLimitsRequest](docs/Model/SetRateLimitsRequest.md)
- [SetSessionLimitsRequest](docs/Model/SetSessionLimitsRequest.md)
- [SetSubjectLimitsRequest](docs/Model/SetSubjectLimitsRequest.md)
- [SortOrder](docs/Model/SortOrder.md)
- [StatusInfo](docs/Model/StatusInfo.md)
- [SubjectCreateRequest](docs/Model/SubjectCreateRequest.md)
- [SubjectIdentifierType](docs/Model/SubjectIdentifierType.md)
- [SubjectRemoveRequest](docs/Model/SubjectRemoveRequest.md)
- [SubjectType](docs/Model/SubjectType.md)
- [SubordinateEntityRole](docs/Model/SubordinateEntityRole.md)
- [SubordinateEntityRoleType](docs/Model/SubordinateEntityRoleType.md)
- [SubordinateEntityRolesQueryRequest](docs/Model/SubordinateEntityRolesQueryRequest.md)
- [SubordinateRoleSubordinateEntityIdentifier](docs/Model/SubordinateRoleSubordinateEntityIdentifier.md)
- [SubordinateRoleSubordinateEntityIdentifierType](docs/Model/SubordinateRoleSubordinateEntityIdentifierType.md)
- [Subunit](docs/Model/Subunit.md)
- [SubunitPermission](docs/Model/SubunitPermission.md)
- [SubunitPermissionScope](docs/Model/SubunitPermissionScope.md)
- [SubunitPermissionsAuthorIdentifier](docs/Model/SubunitPermissionsAuthorIdentifier.md)
- [SubunitPermissionsAuthorIdentifierType](docs/Model/SubunitPermissionsAuthorIdentifierType.md)
- [SubunitPermissionsAuthorizedIdentifier](docs/Model/SubunitPermissionsAuthorizedIdentifier.md)
- [SubunitPermissionsContextIdentifier](docs/Model/SubunitPermissionsContextIdentifier.md)
- [SubunitPermissionsContextIdentifierType](docs/Model/SubunitPermissionsContextIdentifierType.md)
- [SubunitPermissionsGrantRequest](docs/Model/SubunitPermissionsGrantRequest.md)
- [SubunitPermissionsQueryRequest](docs/Model/SubunitPermissionsQueryRequest.md)
- [SubunitPermissionsSubjectIdentifier](docs/Model/SubunitPermissionsSubjectIdentifier.md)
- [SubunitPermissionsSubjectIdentifierType](docs/Model/SubunitPermissionsSubjectIdentifierType.md)
- [SubunitPermissionsSubunitIdentifier](docs/Model/SubunitPermissionsSubunitIdentifier.md)
- [SubunitPermissionsSubunitIdentifierType](docs/Model/SubunitPermissionsSubunitIdentifierType.md)
- [TestDataAuthorizedIdentifier](docs/Model/TestDataAuthorizedIdentifier.md)
- [TestDataAuthorizedIdentifierType](docs/Model/TestDataAuthorizedIdentifierType.md)
- [TestDataContextIdentifier](docs/Model/TestDataContextIdentifier.md)
- [TestDataContextIdentifierType](docs/Model/TestDataContextIdentifierType.md)
- [TestDataPermission](docs/Model/TestDataPermission.md)
- [TestDataPermissionType](docs/Model/TestDataPermissionType.md)
- [TestDataPermissionsGrantRequest](docs/Model/TestDataPermissionsGrantRequest.md)
- [TestDataPermissionsRevokeRequest](docs/Model/TestDataPermissionsRevokeRequest.md)
- [ThirdSubjectIdentifierType](docs/Model/ThirdSubjectIdentifierType.md)
- [TokenAuthorIdentifierType](docs/Model/TokenAuthorIdentifierType.md)
- [TokenAuthorIdentifierTypeIdentifier](docs/Model/TokenAuthorIdentifierTypeIdentifier.md)
- [TokenContextIdentifierType](docs/Model/TokenContextIdentifierType.md)
- [TokenContextIdentifierTypeIdentifier](docs/Model/TokenContextIdentifierTypeIdentifier.md)
- [TokenInfo](docs/Model/TokenInfo.md)
- [TokenPermissionType](docs/Model/TokenPermissionType.md)
- [TokenStatusResponse](docs/Model/TokenStatusResponse.md)
- [UpoPageResponse](docs/Model/UpoPageResponse.md)
- [UpoResponse](docs/Model/UpoResponse.md)

## Authorization

### Bearer

- **Type**: Bearer authentication (JWT)


### SessionToken

- **Type**: API key
- **API key parameter name**: SessionToken
- **Location**: HTTP header


## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `v2`
    - Generator version: `7.14.0`
- Build package: `org.openapitools.codegen.languages.PhpNextgenClientCodegen`
