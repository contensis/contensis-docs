1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Renderers

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

DELETE/api/management/projects/**{projectId}**/renderers/**{rendererId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**rendererId***(required)*

path

string

The renderer identifier

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

Renderer not found

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
DELETE: /api/management/projects/movieDb/renderers/top-movie-listing
```