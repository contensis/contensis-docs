1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Domains](/help-and-docs/apis/management-http/domains)

[Log in to add to favourites](/account/login)

Page last updated 27 June 2024

PATCH/api/management/projects/**{projectId}**/domains/**{domainId}**

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

[Domain](/help-and-docs/apis/management-http/domains)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Domain not found

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Update the host header for a domain

HTTP

```
PATCH: /api/management/projects/movieDb/domains/8fed8722-cd09-44f1-9e42-bd4e8a703213

{
	"hostHeader": "www.mysite.com"
}
```

Update a domain to be your primary domain

HTTP

```
PATCH: /api/management/projects/movieDb/domains/8fed8722-cd09-44f1-9e42-bd4e8a703213

{
	"isPrimary": true
}
```