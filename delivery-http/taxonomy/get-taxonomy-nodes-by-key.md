1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Delivery API](/help-and-docs/apis/delivery-http)
4.  [Taxonomy](/help-and-docs/apis/delivery-http/taxonomy)

[Log in to add to favourites](/account/login)

Page last updated 15 June 2020

GETGET: /api/delivery/projects/**{projectId}**/taxonomy/nodes/**{key}**

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

**key***(required)*

path

string

\-

The taxonomy key

**language**

query

string

language

The specified language for the node. If no value is provided then the menu order is removed for all languages

**childDepth**

query

number

integer

The maximum depth to which child nodes should be returned

**order**

query

string

\-

A comma-separated list of the field Ids to order the results by. Prefix field Id with - for descending order.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Taxonomy](/help-and-docs/apis/delivery-http/taxonomy)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Taxonomy not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/delivery/projects/movieDb/taxonomy/nodes/0/1/2?language=en-GB&childDepth=2&order=defined
```