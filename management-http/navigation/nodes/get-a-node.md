## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Navigation
5.  [Node](/help-and-docs/apis/management-http/navigation/nodes)

[Log in to add to favourites](/account/login)

Page last updated 22 June 2020

GET/api/management/projects/**{projectId}**/nodes/**{nodeId}**/

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

## Responses

HTTP status code

Reason

Model

**200**

Success

[Node](/help-and-docs/apis/management-http/navigation/nodes)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

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
GET: /api/management/projects/website/nodes/d6bdea41-729c-4a07-85bf-a392aa0afc2b
```