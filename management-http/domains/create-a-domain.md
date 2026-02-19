1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Domains](https://www.contensis.com/help-and-docs/apis/management-http/domains)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 June 2024

POST/api/management/projects/**{projectId}**/domains/

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

**Domain***(required)*

body

object

[domain](https://www.contensis.com/help-and-docs/apis/management-http/domains)

The domain to create.

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

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Create a new domain for a specifc project

JSON

```
POST: /api/management/projects/movies/domains/

{
	"hostHeader": "www.mysite.com"
}
```

## Remarks

The first domain created will be set as your primary domain. Subsequent domains created will be set to *isPrimary = false* unless you specifically set *isPrimary = true* as part of the POST data.