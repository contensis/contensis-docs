1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](/account/login)

Page last updated 22 June 2020

DELETE/api/management/projects/**{projectId}**/nodes/**{parentNodeId}**/children/order

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

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Parent node not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Language is invalid

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

The example below is deleting the node order specifically for French.

HTTP

```
DELETE: /api/management/projects/website/nodes/62722a79-4507-4969-b65e-f6c769ce1336/children/order?language=fr
```