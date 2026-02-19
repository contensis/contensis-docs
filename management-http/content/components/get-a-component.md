1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  [Components](/help-and-docs/apis/management-http/content/components)

[Log in to add to favourites](/account/login)

Page last updated 22 July 2020

GET/api/management/projects/**{projectId}**/components/**{componentId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**componentId***(required)*

path

string

The component identifier.

**versionStatus**

query

string

The status of the associated entry, either published or latest. The default is published

**version**

query

string

The version number of the resource. {major}.{minor} e.g. 1.2

## Responses

HTTP status code

Reason

Model

**200**

Success

[Component](/help-and-docs/apis/management-http/content/components)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Component not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/movieDb/components/movieRole/
```