## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 January 2023

GET/api/management/projects/**{projectId}**/blocks/**{blockId}**

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

## Responses

HTTP status code

Reason

Model

**200**

Success

[Block](https://www.contensis.com/help-and-docs/apis/management-http/publishing/blocks/block)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Example request

HTTP

```
Accept: application/json
GET: /api/management/projects/movieDb/blocks/movie-listing
```