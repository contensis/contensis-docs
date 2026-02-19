1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Permissions overview](https://www.contensis.com/help-and-docs/apis/management-http/security/permissions)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 July 2021

GET/api/management/projects/**{projectId}**/security/permissions/**{resourceType}**/?userId=**{userId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**resourceType***(required)*

path

string

The type of resource to retrieve permissions for. Permitted values are: assets, audiences, blocks, comments, contenttypes, domains, entries, eventstreams, forms, manifests, nodes, proxies, redirects, renderers, signals, views, webhooksubscriptions

**userId***(required)*

query

string

The id of the user to retrieve permissions for.

## Responses

HTTP status code

Reason

Model

**200**

Success

**404**

Entry not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/movieDb/security/permissions/webhookSubscriptions/?userId=a.user
```