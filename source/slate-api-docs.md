--- 

title: Enterprise Search for European Commission - Search API 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

Specifications of Search API 

**Version:** DEV 

# /CAS-CLIENT/REGISTERSESSION
## ***GET*** 

**Summary:** RegisterSession

### HTTP Request 
`***GET*** /cas-client/registerSession` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| proxyTicket | query | proxyTicket | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /CAS-CLIENT/USER
## ***GET*** 

**Summary:** GetUser

**Description:** <strong>Only for browser call (use http session)</strong><br>This method allow to retrieve the current user associate to the session.

### HTTP Request 
`***GET*** /cas-client/user` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| sessionToken | query | sessionToken | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /CAS-CLIENT/VALIDATESESSIONTOKEN
## ***GET*** 

**Summary:** validateSessionToken

**Description:** Validates if your session token is still valid

### HTTP Request 
`***GET*** /cas-client/validateSessionToken` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| sessionToken | query | sessionToken | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/AUTOCOMPLETE
## ***GET*** 

**Summary:** Autocomplete

**Description:** <strong>Returns a list of possible values to complete a search phrase</strong><br><br>Autocomplete functionality

### HTTP Request 
`***GET*** /rest/autocomplete` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | No | string |
| text | query | text | Yes | string |
| language | query | Search language respecting <a href="http://www.loc.gov/standards/iso639-2/php/English_list.php">ISO 639-1</a><br>Defaults to English | No | string |
| sessionToken | query | sessionToken | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/CLICK
## ***GET*** 

**Summary:** Click

**Description:** <span>Internal use ONLY</span> Manage user clicks on document/result

### HTTP Request 
`***GET*** /rest/click` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| data | query | data | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/DOCUMENT/{REFERENCE}
## ***GET*** 

**Summary:** DocumentDetail

**Description:** <span style="color:blue">Was previously only internal, now accessible for highlighting</span>

### HTTP Request 
`***GET*** /rest/document/{reference}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| reference | path | reference | Yes | string |
| text | query | text | No | string |
| highlight | query | highlight | No | string |
| pageNumber | query | pageNumber | No | integer |
| sessionToken | query | sessionToken | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/DOCUMENT/{REFERENCE}/EXIST
## ***GET*** 

**Summary:** documentExist

**Description:** Check if a document exists with reference

### HTTP Request 
`***GET*** /rest/document/{reference}/exist` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| reference | path | reference | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/DOCUMENT/{REFERENCE}/RELATED
## ***GET*** 

**Summary:** RelatedSearch

**Description:** RelatedSearch

### HTTP Request 
`***GET*** /rest/document/{reference}/related` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| reference | path | reference | Yes | string |
| facetFiltering | query | Formated like : KEY1=VALUE1,VALUE2;KEY2=VALUE3 | No | string |
| highlight | query | highlight | No | string |
| language | query | Search language respecting <a href="http://www.loc.gov/standards/iso639-2/php/English_list.php">ISO 639-1</a>, Defaults to en if not specified | No | string |
| grouped | query | grouped | No | boolean |
| pageSize | query | pageSize | No | integer |
| pageNumber | query | pageNumber | No | integer |
| sessionToken | query | sessionToken that <b>Enterprise Search</b> provided after a Proxy Ticket | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/DOCUMENT/{REFERENCE}/RELATED/ADVANCED
## ***POST*** 

**Summary:** Advanced Releated Search

**Description:** <strong>Search the index for documents</strong><br><br>Advanced Related search use case

### HTTP Request 
`***POST*** /rest/document/{reference}/related/advanced` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| reference | path | reference | Yes | string |
| highlight | query | highlight | No | string |
| languages | query | Search language respecting <a href="http://www.loc.gov/standards/iso639-2/php/English_list.php">ISO 639-1</a><br>Multiple languages possible, ie : en,fr,de,nl | No | array |
| grouped | query | grouped | No | boolean |
| pageSize | query | pageSize | No | integer |
| pageNumber | query | pageNumber | No | integer |
| sessionToken | query | sessionToken that <b>Enterprise Search</b> provided after a Proxy Ticket | No | string |
| metadata | body | &bull;<b>Metadatum must be known by Enterprise Search</b><br><a href='https://webgate.ec.europa.eu/CITnet/confluence/display/SEARCH/Advanced+Search+Parameters'>Syntax documentation available here</a> | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /REST/FACET/
## ***GET*** 

**Summary:** SearchFacets

**Description:** <strong>Returns a facet list</strong><br><br>The primary use case for the facet search is to build up the facet structure in the GUI. The information displayed is based on the query parameters that the user has entered, the field criteria that the front-end application enriches and optionally the facets that the user previously had selected.

### HTTP Request 
`***GET*** /rest/facet/` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| text | query | text | Yes | string |
| maxvalues | query | maximum amount of facet values returned, default -1 for ALL | No | integer |
| language | query | Query language | No | string |
| beginDate | query |  This field is the begin date to find the documents having PUBLISHDATE within a specific range of dates.<br>Use pattern : yyyy-MM-dd'T'HH:mm:ss.SSSZ | No | dateTime |
| endDate | query | This field is the end date to find the documents having PUBLISHDATE within a specific range of dates.<br>Use pattern : yyyy-MM-dd'T'HH:mm:ss.SSSZ | No | dateTime |
| sessionToken | query | Facet type to return, default is FACET, values : FACET | No | string |
| group | query | group | No | boolean |
| metadata | query | &bull;<b>Metadatum must be known by Enterprise Search</b><br>&bull;By default, Enterprise Search allows 'PUBLISHDATE','EXPIRATIONDATE' and 'SUBTITLE'<br>&bull;Other metadatum should be described in a functional document in accordance with Enterprise Search team<br>&bull;When a value represents a date, then it should match <a href='http://en.wikipedia.org/wiki/ISO_8601'>ISO-8601</a> representation<br>&bull;Multiple values per fields is supported<br>Sample : <code>{"FIELD1":["VALUE1","VALUE2"],"FIELD2":["VALUE1","VALUE2"]}</code> | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/FACET/ADVANCED
## ***POST*** 

**Summary:** SearchFacets

**Description:** <strong>Returns a facet list</strong><br><br>The primary use case for the facet search is to build up the facet structure in the GUI. The information displayed is based on the query parameters that the user has entered, the field criteria that the front-end application enriches and optionally the facets that the user previously had selected.

### HTTP Request 
`***POST*** /rest/facet/advanced` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| text | query | text | No | string |
| maxvalues | query | maximum amount of facet values returned, default -1 for ALL | No | integer |
| languages | query | languages | No | array |
| beginDate | query | beginDate | No | dateTime |
| endDate | query | endDate | No | dateTime |
| group | query | group | No | boolean |
| sessionToken | query | sessionToken | No | string |
| sort | query | sort | No | string |
| metadata | body | &bull;<b>Metadatum must be known by Enterprise Search</b><br><a href='https://webgate.ec.europa.eu/CITnet/confluence/display/SEARCH/Advanced+Search+Parameters'>Syntax documentation available here</a> | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /REST/REDIRECT
## ***GET*** 

**Summary:** Redirect

**Description:** <span>External use</span> Manage user clicks on document/result

### HTTP Request 
`***GET*** /rest/redirect` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| data | query | data | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/SEARCH
## ***GET*** 

**Summary:** Simple Search

**Description:** <strong>Search the index for documents</strong><br><br>General search use case

### HTTP Request 
`***GET*** /rest/search` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| text | query | text | Yes | string |
| highlight | query | highlight | No | string |
| language | query | Search language respecting <a href="http://www.loc.gov/standards/iso639-2/php/English_list.php">ISO 639-1</a> | Yes | string |
| pageSize | query | pageSize | No | integer |
| pageNumber | query | pageNumber | No | integer |
| group | query | group | No | boolean |
| sort | query | Sort by date/relavancy by default: it is relavancy, to sort by date give value <b>date</b> | No | string |
| beginDate | query |  This field is the begin date to find the documents having PUBLISHDATE within a specific range of dates.<br>Use pattern : yyyy-MM-dd'T'HH:mm:ss.SSSZ | No | dateTime |
| endDate | query | This field is the end date to find the documents having PUBLISHDATE within a specific range of dates.<br>Use pattern : yyyy-MM-dd'T'HH:mm:ss.SSSZ | No | dateTime |
| sessionToken | query | sessionToken that <b>Enterprise Search</b> provided after a Proxy Ticket | No | string |
| metadata | query | &bull;<b>Metadatum must be known by Enterprise Search</b><br>&bull;By default, Enterprise Search allows 'PUBLISHDATE','EXPIRATIONDATE' and 'SUBTITLE'<br>&bull;Other metadatum should be described in a functional document in accordance with Enterprise Search team<br>&bull;When a value represents a date, then it should match <a href='http://en.wikipedia.org/wiki/ISO_8601'>ISO-8601</a> representation<br>&bull;Multiple values per fields is supported<br>Sample : <code>{"FIELD1":["VALUE1","VALUE2"],"FIELD2":["VALUE1","VALUE2"]}</code> | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/SEARCH/ADVANCED
## ***POST*** 

**Summary:** Advanced Search

**Description:** <strong>Search the index for documents</strong><br><br>Advanced search use case

### HTTP Request 
`***POST*** /rest/search/advanced` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| text | query | text | Yes | string |
| languages | query | Search language respecting <a href="http://www.loc.gov/standards/iso639-2/php/English_list.php">ISO 639-1</a><br>Multiple languages possible, ie : en,fr,de,nl | Yes | array |
| pageNumber | query | pageNumber | No | integer |
| pageSize | query | pageSize | No | integer |
| beginDate | query |  This field is the begin date to find the documents having PUBLISHDATE within a specific range of dates.<br>Use pattern : yyyy-MM-dd'T'HH:mm:ss.SSSZ | No | dateTime |
| endDate | query | This field is the end date to find the documents having PUBLISHDATE within a specific range of dates.<br>Use pattern : yyyy-MM-dd'T'HH:mm:ss.SSSZ | No | dateTime |
| sort | query | Sort by date/relavancy by default: it is relavancy, to sort by date give value <b>date</b> | No | string |
| highlight | query | highlight | No | string |
| group | query | group | No | boolean |
| groupBySortField | query | groupBySortField | No | string |
| highlightSize | query | highlightSize | No | integer |
| sessionToken | query | sessionToken that <b>Enterprise Search</b> provided after a Proxy Ticket | No | string |
| metadata | body | &bull;<b>Metadatum must be known by Enterprise Search</b><br><a href='https://webgate.ec.europa.eu/CITnet/confluence/display/SEARCH/Advanced+Search+Parameters'>Syntax documentation available here</a> | No |  |
| groupByParentQuery | body | &bull;<b>Metadatum must be known by Enterprise Search</b><br><a href='https://webgate.ec.europa.eu/CITnet/confluence/display/SEARCH/Advanced+Search+Parameters'>Syntax documentation available here</a> | No |  |
| groupByInclude | body | Grouped Search Filter on 1st level grouped ID's | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /REST/SEARCH/SUGGESTIONS
## ***GET*** 

**Summary:** suggestions

### HTTP Request 
`***GET*** /rest/search/suggestions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| text | query | text | Yes | string |
| language | query | language | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/SOCIAL/GETNOTIFICATIONBYID
## ***GET*** 

**Summary:** getNotificationById

**Description:** Gets user notification

### HTTP Request 
`***GET*** /rest/social/getNotificationById` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | query | id | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/SOCIAL/GETNOTIFICATIONS
## ***GET*** 

**Summary:** getNotification

**Description:** Gets user notifications

### HTTP Request 
`***GET*** /rest/social/getNotifications` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| userId | query | userId | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/SOCIAL/PUSHNOTIFICATION
## ***POST*** 

**Summary:** pushNotification

**Description:** Sends a notification to user

### HTTP Request 
`***POST*** /rest/social/pushNotification` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| userId | query | userId | Yes | string |
| reference | query | reference | Yes | string |
| apikey | query | apikey | Yes | string |
| type | query | type | Yes | string |
| sendMail | query | sendMail | Yes | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /REST/SOCIAL/UPDATENOTIFICATION
## ***POST*** 

**Summary:** updateNotification

**Description:** Gets user notifications

### HTTP Request 
`***POST*** /rest/social/updateNotification` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | query | id | Yes | long |
| reference | query | reference | Yes | string |
| apikey | query | apikey | Yes | string |
| enabled | query | enabled | Yes | boolean |
| userId | query | userId | Yes | string |
| type | query | type | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /REST/TRANSLATION/GETTRANSLATION
## ***GET*** 

**Summary:** translation

### HTTP Request 
`***GET*** /rest/translation/getTranslation` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| key | query | key | Yes | string |
| language | query | language | Yes | string |
| defaultValue | query | defaultValue | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/TRANSLATION/GETTRANSLATIONS
## ***GET*** 

**Summary:** translations

### HTTP Request 
`***GET*** /rest/translation/getTranslations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |
| language | query | language | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/USERS/GETUSER
## ***GET*** 

**Summary:** Users

**Description:** Returns a specific user

### HTTP Request 
`***GET*** /rest/users/getUser` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| userId | query | userId | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/USERS/SEARCH
## ***GET*** 

**Summary:** Users

**Description:** Returns users containing keyword

### HTTP Request 
`***GET*** /rest/users/search` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| keyword | query | keyword | Yes | string |
| page | query | page | No | integer |
| pageSize | query | pageSize | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/UTILITIES/GETALLLANGUAGES
## ***GET*** 

**Summary:** Retrieve all available languages

**Description:** <strong>Returns All Languages available in Enterprise Search</strong>

### HTTP Request 
`***GET*** /rest/utilities/getAllLanguages` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/UTILITIES/GETAPIKEYS
## ***GET*** 

**Summary:** Retrieve all ApiKeys

**Description:** <strong>Returns All ApiKeys provided by Enterprise Search</strong>

### HTTP Request 
`***GET*** /rest/utilities/getApiKeys` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

# /REST/UTILITIES/GETTEMPLATES
## ***GET*** 

**Summary:** GetTemplatestemplate names to use with this apiKey

**Description:** <strong>Returns template names from an apiKey</strong><br>Provide search template name and ingestion template name related to an application

### HTTP Request 
`***GET*** /rest/utilities/getTemplates` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| apiKey | query | apiKey | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Bad request |
| 401 | Unauthorized |
| 500 | Internal server error |
| 501 | Not implemented |
| 503 | Service unavailable |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
