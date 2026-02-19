1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  proxies

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

GET/api/management/projects/**{projectId}**/proxies?versionstatus=**{versionStatus}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**versionStatus**

query

string

The status of the associated proxy, either published or latest. The default is published

## Responses

HTTP status code

Reason

Model

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/website/proxies/
```