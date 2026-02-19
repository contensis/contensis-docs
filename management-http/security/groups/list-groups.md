1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [Groups](/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](/account/login)

Page last updated 29 December 2023

GET/api/security/groups/?order=**{order}**&q=**{q}**&zenql=**{zenql}**&pageIndex=**{pageIndex}**&pageSize=**{pageSize}**

## Parameters

Name

Parameter type

Type

Format

Description

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

**q**

query

string

\-

A simple query to perform a 'contains' search over key properties.

**order**

query

string

\-

A comma-separated list of the field Ids to order the results by. Prefix field Id with - for descending order.

**zenql**

query

string

\-

ZenQL query to select the groups returned in the listing

## Responses

HTTP status code

Reason

Model

**200**

Success

[Group](/help-and-docs/apis/management-http/security/groups)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get a list of groups with the name containing the word 'mayhem'

HTTP

```
GET: /api/security/groups?q=mayhem
```

## Remarks

**Permissions**

Member of `System Administrators`.