1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Domains](https://www.contensis.com/help-and-docs/apis/management-http/domains)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 26 June 2024

GET/api/management/projects/**{projectId}**/domains/

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

## Responses

HTTP status code

Reason

Model

**200**

Success

[Domain](https://www.contensis.com/help-and-docs/apis/management-http/domains)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get all domains ordered by host header in pages of 10

HTTP

```
GET: /api/management/projects/movieDb/domains/?order=hostHeader&pageSize=10
```