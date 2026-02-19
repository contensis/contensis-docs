1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  Navigation
5.  [Nodes](https://www.contensis.com/help-and-docs/apis/delivery-http/navigation/nodes)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 22 June 2020

GET/api/delivery/projects/**{projectId}**/nodes/**{nodeId}**/ancestors

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

**startLevel**

query

number

integer

The level of the top ancestor node to return. If no value is provided then the level will be 1 (root)

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
GET: /api/delivery/projects/movieDb/nodes/d014533c-2f4e-4f73-b9f5-ff107755080b/ancestors?language=en-GB&depth=1&versionStatus=latest
```

## Remarks

The nodes will be returned in level order ascending, i.e. root -> leaf. If the node is the root, then an empty list will be returned.