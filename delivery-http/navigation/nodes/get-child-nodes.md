1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  Navigation
5.  [Nodes](https://www.contensis.com/help-and-docs/apis/delivery-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 11 January 2024

GET/api/delivery/projects/**{projectId}**/nodes/**{nodeId}**/children

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

**language**

query

string

language

The specified language for the node. If no value is provided then the menu order is removed for all languages

**versionStatus**

query

string

\-

The status of the associated entry, either published or latest. The default is published

**entryFields**

query

string

\-

A comma separated list of entry fields to include in the entry response. Specify \* to include all entry fields

**entryLinkDepth**

query

number

\-

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10

**entryFieldLinkDepths**

query

object

\-

Link depths for specific field paths to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10 (version 16+ only)

## Responses

HTTP status code

Reason

Model

**200**

Success

[Node](https://www.contensis.com/help-and-docs/apis/management-http/navigation/nodes)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Node not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/delivery/projects/movieDb/nodes/d014533c-2f4e-4f73-b9f5-ff107755080b/children?language=en-GB&versionStatus=latest
```

## Remarks

If an order has been set for the child nodes then they will be returned in the defined order, otherise they will be returned ordered by the created date ascending.