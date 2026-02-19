## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [redirects](https://www.contensis.com/help-and-docs/apis/management-http/redirects)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 July 2024

DELETE/api/management/projects/**{projectId}**/redirects/**{redirectId}**

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

**redirectId***(required)*

path

string

guid

The redirect identifier

## Responses

HTTP status code

Reason

Model

**204**

Success

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Redirect not found

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
DELETE: /api/management/projects/movieDb/redirects/8afecff2-eb7f-4501-b1a7-80a49bdfb932
```