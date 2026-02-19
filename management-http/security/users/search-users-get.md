1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 June 2024

GET/api/security/users/search?order=**{order}**&where=**{where}**&orderBy=**{orderBy}**&pageIndex=**{pageIndex}**&pageSize=**{pageSize}**

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

**orderBy**

query

string

\-

An array of order by objects

**where**

query

string

[\-](https://www.contensis.com/help-and-docs/apis/delivery-http/search-basics/query-operators)

An expression array of query operator objects

## Responses

HTTP status code

Reason

Model

**200**

Success

[User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get the first page of 5 users that contain the word tyler in the username or email

HTTP

```
GET: /api/security/users?pageSize=5&where=[{"or":[{"field":"Username","contains":"tyler"},{"field":"Email","contains":"tyler"}]}]
```

## Remarks

**Permissions**

Member of `System Administrators`.