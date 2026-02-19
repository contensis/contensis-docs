1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Components](https://www.contensis.com/help-and-docs/apis/management-http/content/components)

[Log in to add to favourites](https://www.contensis.com/account/login)

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

[Component](https://www.contensis.com/help-and-docs/apis/management-http/content/components)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Component not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/movieDb/components/movieRole/
```