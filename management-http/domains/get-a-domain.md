## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Domains](https://www.contensis.com/help-and-docs/apis/management-http/domains)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 26 June 2024

GET/api/management/projects/**{projectId}**/domains/**{domainId}**

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

**domainId***(required)*

path

string

guid

The domain identifier.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Domain](https://www.contensis.com/help-and-docs/apis/management-http/domains)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Domain not found

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get a domain

HTTP

```
GET: /api/management/projects/movieDb/domains/8fed8722-cd09-44f1-9e42-bd4e8a703213
```