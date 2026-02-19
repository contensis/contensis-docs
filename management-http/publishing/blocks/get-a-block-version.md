1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

GET/api/management/projects/**{projectId}**/blocks/**{blockId}**/branches/**{branchId}**/versions/**{version}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**blockId***(required)*

path

string

The block identifier

**branchId***(required)*

path

string

The branch identifier

**version***(required)*

path

string

A label of either live or latest, or a valid version number.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Block version](/help-and-docs/apis/management-http/publishing/blocks/block-version)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get latest version of a block

HTTP

```
Accept: application/json
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/latest
```

Get the current live version of a block

HTTP

```
Accept: application/json
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/live
```

Get version 2 of a block

HTTP

```
Accept: application/json
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/2
```