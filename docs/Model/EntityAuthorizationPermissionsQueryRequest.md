# # EntityAuthorizationPermissionsQueryRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**authorizing_identifier** | [**\NetSeven\KseF2Model\EntityAuthorizationsAuthorizingEntityIdentifier**](EntityAuthorizationsAuthorizingEntityIdentifier.md) | Identyfikator podmiotu uprawniającego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | [optional]
**authorized_identifier** | [**\NetSeven\KseF2Model\EntityAuthorizationsAuthorizedEntityIdentifier**](EntityAuthorizationsAuthorizedEntityIdentifier.md) | Identyfikator podmiotu uprawnionego. | Type | Value | | --- | --- | | Nip | 10 cyfrowy numer NIP | | PeppolId | Identyfikator dostawcy usług Peppol | | [optional]
**query_type** | [**\NetSeven\KseF2Model\QueryType**](QueryType.md) | Typ zapytania. | Type | Value | | --- | --- | | Granted | Uprawnienia nadane innym podmiotom | | Received | Uprawnienia otrzymane od innych podmiotów | |
**permission_types** | [**\NetSeven\KseF2Model\InvoicePermissionType[]**](InvoicePermissionType.md) | Lista rodzajów wyszukiwanych uprawnień. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
