1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  Content
5.  [Entry](https://www.contensis.com/help-and-docs/apis/delivery-http/content/entry)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 11 January 2024

GET/api/delivery/projects/**{projectId}**/contenttypes/**{contentTypeId}**/entries

## Parameters

Name

Parameter type

Type

Format

Description

**projectId***(required)*

path

string

\-

The project identifier found in the project overview screen of the management console.

**contentTypeId***(required)*

path

string

\-

The content type identifier.

**versionStatus**

query

string

\-

The status of the associated entry, either published or latest. The default is published

**linkDepth**

query

number

integer

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10

**pageIndex**

query

number

integer

The index of the page.

**pageSize**

query

number

integer

The number of results per page. The default is 25.

**order**

query

string

\-

A comma-separated list of the field Ids to order the results by. Prefix field Id with - for descending order.

**fields**

query

string

\-

A comma-separated list of field ids to restrict the fields returned for an entry

**language**

path

string\[...\]

language

A comma separated list of variations to delete

**fieldLinkDepths**

query

object

\-

Link depths for specific field paths to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10 (version 16+ only)

## Responses

HTTP status code

Reason

Model

**200**

Success

[Entry](https://www.contensis.com/help-and-docs/apis/management-http/content/entries)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Content type not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

List of all movie entries

HTTP

```
GET: /api/delivery/projects/movieDb/contentTypes/movies/entries/
```

List of all movie entries translated to German

HTTP

```
GET: /api/delivery/projects/movieDb/contentTypes/movies/entries?language=de
```

List of all movie entries translated to German and ordered by release date descending

HTTP

```
GET: /api/delivery/projects/movieDb/contentTypes/movies/entries?language=de&order=-releaseDate
```

List of all movie entries with their direct child entries, assets and images resolved

HTTP

```
GET: /api/delivery/projects/movieDb/contentTypes/movies/entries?linkDepth=1
```

List of all movie entries with direct child entries, assets and images resolved for only two fields (version 16+ only)

HTTP

```
GET: /api/delivery/projects/movieDb/contentTypes/movies/entries?fieldLinkDepths={"director":1,"actors":2}
```

List the latest version of all movies

HTTP

```
GET: /api/delivery/projects/movieDb/contentTypes/movies/entries?versionStatus=latest
```