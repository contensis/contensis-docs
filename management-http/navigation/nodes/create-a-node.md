1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 October 2021

POST/api/management/projects/**{projectId}**/nodes/**{parentNodeId}**/children

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

**node***(required)*

body

object

node

The node object to update

## Responses

HTTP status code

Reason

Model

**201**

Created

[Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Parent node not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

An example of posting all fields to create a node

JSON

```
POST: /api/management/projects/website/nodes/f3322e4f-72b5-4064-be88-fcfed6c82635/children

{
    "id": "d6bdea41-729c-4a07-85bf-a392aa0afc2b",
    "parentId": "f3322e4f-72b5-4064-be88-fcfed6c82635",
    "displayName": {
        "en-GB": "Fight club",
        "fr-FR": "Club de combat"
    },
    "slug": {
        "en-GB": "fight-club",
    "fr-FR": "club-de-combat"
    },
    "restrictedToLanguages": [
        "en-GB",
        "fr-FR"
    ],
    "entryId": "9272ac06-1b3a-4e68-ac1b-a05828b0f7d6",
    "includeInMenu": true
}
```

Minimum fields required to create a node

JSON

```
POST: /api/management/projects/website/nodes/f3322e4f-72b5-4064-be88-fcfed6c82635/children

{
    "parentId": "f3322e4f-72b5-4064-be88-fcfed6c82635",
    "displayName": {
        "en-GB": "Fight club"
    }
}
```