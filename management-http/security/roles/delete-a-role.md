## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Role](https://www.contensis.com/help-and-docs/apis/management-http/security/roles)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2020

DELETE/api/management/projects/**{projectId}**/security/roles/**{roleId}**

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

**roleId***(required)*

path

string

uuid

The role identifier.

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

Role not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Delete a role by Id

HTTP

```
DELETE: /api/management/projects/movieDb/security/roles/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```