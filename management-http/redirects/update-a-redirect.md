## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [redirects](https://www.contensis.com/help-and-docs/apis/management-http/redirects)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 July 2024

PATCH/api/management/projects/**{projectId}**/redirects/**{redirectId}**

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

**200**

Success

[Redirect](https://www.contensis.com/help-and-docs/apis/management-http/redirects)

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

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Update the status code of a redirect

HTTP

```
PATCH: api/management/projects/{project}/redirects/17c21990-2470-403d-a843-77106e9e5e4f
{
	"statusCode": 302
}
```