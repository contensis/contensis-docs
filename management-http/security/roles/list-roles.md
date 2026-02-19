1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Role](https://www.contensis.com/help-and-docs/apis/management-http/security/roles)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2020

GET/api/management/projects/**{projectId}**/security/roles

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

## Responses

HTTP status code

Reason

Model

**200**

Success

[Role](https://www.contensis.com/help-and-docs/apis/management-http/security/roles)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

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

List roles with paging options

HTTP

```
GET: /api/management/projects/movieDb/security/roles?pageIndex=1&pageSize=5
```

## Remarks

In order to list roles you must be a member of the "System Administrators" user group. If you do not have permission to list roles you will get a 403 Forbidden response.