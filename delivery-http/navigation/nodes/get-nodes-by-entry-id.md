1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Delivery API](/help-and-docs/apis/delivery-http)
4.  Navigation
5.  [Nodes](/help-and-docs/apis/delivery-http/navigation/nodes)

[Log in to add to favourites](/account/login)

Page last updated 11 January 2024

GET/api/delivery/projects/**{projectId}**/nodes/?entryId=**{entryId}**

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

**entryId***(required)*

query

string

uuid

The entry identifier as a 128 bit GUID

**language**

query

string

language

The specified language for the node. If no value is provided then the menu order is removed for all languages

**depth**

query

number

\-

The depth of descendants to include for the node. The default is 0. This parameter only has an effect if canonicalOnly has a value of true

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

**canonicalOnly**

query

boolean

\-

If canonicalOnly is true then just the canonical (default location) node is returned, otherwise a list of all nodes attached to the specified entry are returned

## Responses

HTTP status code

Reason

Model

**200**

Success when canonicalOnly is not set or is false

[Node](/help-and-docs/apis/management-http/navigation/nodes)

**200**

Success when canonicalOnly is true

[Node](/help-and-docs/apis/management-http/navigation/nodes)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Node not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/delivery/projects/movieDb/nodes/?entryId=d014533c-2f4e-4f73-b9f5-ff107755080b&language=en-GB&depth=1&versionStatus=latest
```