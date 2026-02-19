## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  [Components](/help-and-docs/apis/management-http/content/components)

[Log in to add to favourites](/account/login)

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

[Component](/help-and-docs/apis/management-http/content/components)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/movieDb/components?versionStatus=published
```