1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 14 October 2021

PUT/api/management/projects/**{projectId}**/nodes/**{parentNodeId}**/children/order

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

**language**

query

string

language

The specified language for the node. If no value is provided then the menu order is removed for all languages

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

Parent node not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Language is invalid

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

The example below is setting the node order specifically for French.

JSON

```
PUT: /api/management/projects/website/nodes/62722a79-4507-4969-b65e-f6c769ce1336/children/order?language=fr-FR
[
    "62722a79-4507-4969-b65e-f6c769ce1336",
    "9caa58f7-20f5-44ba-a493-685c88556644",
    "ba77f063-77c9-4416-af1a-8f5002650da3",
    "58277007-6c36-4d46-bdba-3ebb11809f9f",
    "59808362-5f55-4fa8-863f-7cc98c1dafca",
    "30be3bac-e671-41a3-af3e-e2acdebe39f1",
    "43224e9e-15a2-40fc-a41f-b239253cc6f1",
    "7ce5f200-9d7c-4025-bf5c-e611c1e3e6b4",
    "f30a1a70-1bea-4292-a7f8-7477b7943675",
    "c4c751ab-9e7d-4843-9458-f38a39ddbfab",
    "163129f1-f459-4ca5-a200-216778b487b1"
]
```

## Remarks

The default language order is used for other languages if no language specific order is set.