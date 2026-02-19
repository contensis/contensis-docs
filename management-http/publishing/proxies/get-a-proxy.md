1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  publishing
5.  proxies

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 January 2023

GET/api/management/projects/**{projectId}**/proxies/**{proxyId}**?versionstatus=**{versionStatus}**

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

**proxyId***(required)*

path

string

guid

The proxy identifier

**versionStatus**

query

string

\-

The status of the associated proxy, either published or latest. The default is published

## Responses

HTTP status code

Reason

Model

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/website/proxies/ec0b25dc-0c46-4a90-8610-c0886c51b709
```