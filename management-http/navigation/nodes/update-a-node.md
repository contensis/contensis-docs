1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 08 June 2023

PUT/api/management/projects/**{projectId}**/nodes/**{nodeId}**

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

Node not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
PUT: /api/management/projects/website/nodes/d6bdea41-729c-4a07-85bf-a392aa0afc2b

{
    "parentId": "bda31335-136c-42f4-bedc-69660b711a40",
    "displayName": {
        "en-GB": "Blood Meridian"
    },
    "slug": {
        "en-GB": "blood-meridian"
    }
}
```