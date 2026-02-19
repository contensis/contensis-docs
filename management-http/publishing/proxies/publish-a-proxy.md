1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  publishing
5.  proxies

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 January 2023

POST/api/management/projects/**{projectId}**/proxies/**{proxyId}**/workflow/events

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

Publish a proxy

HTTP

```
POST /api/management/projects/movieDb/proxies/a65a22bf-0864-4dc6-8a9d-51063ed3ffba/workflow/events

{
    "version": "0.3",
    "event": "publish"
}
```