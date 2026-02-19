## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Delivery API](/help-and-docs/apis/delivery-http)
4.  Content
5.  [Content types](/help-and-docs/apis/delivery-http/content/content-types)

[Log in to add to favourites](/account/login)

Page last updated 08 November 2023

GET/api/delivery/projects/**{projectId}**/contenttypes/**{contentTypeId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**contentTypeId***(required)*

path

string

The content type identifier.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Content type](/help-and-docs/apis/management-http/content/content-types/content-types)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Content type not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/delivery/projects/movieDb/contenttypes/movie
```