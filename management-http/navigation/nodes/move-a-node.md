1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 05 June 2023

PUT/api/management/projects/**{projectId}**/nodes/**{nodeId}**/parentId

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

**nodeId***(required)*

path

string

uuid

The node identifier as a 128 bit GUID

**node***(required)*

body

object

node

The node object to update

## Responses

HTTP status code

Reason

Model

**204**

Success

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Node not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists in target location

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**204**

Node moved

## Examples

Change the parent id to move the node

HTTP

```
PUT: /api/management/projects/website/nodes/d6bdea41-729c-4a07-85bf-a392aa0afc2b/parentId

"f3322e4f-72b5-4064-be88-fcfed6c82635"
```