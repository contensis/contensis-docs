1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 22 June 2020

GET/api/management/projects/**{projectId}**/nodes/**{parentNodeId}**/children

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

**parentNodeId***(required)*

path

string

uuid

The parent node identifier for the children which have an order.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Parent node not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/website/nodes/f3322e4f-72b5-4064-be88-fcfed6c82635/children
```