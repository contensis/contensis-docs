## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Components](https://www.contensis.com/help-and-docs/apis/management-http/content/components)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 22 June 2020

GET/api/management/projects/**{projectId}**/components/

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**versionStatus**

query

string

The status of the associated entry, either published or latest. The default is published

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

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/movieDb/components?versionStatus=published
```