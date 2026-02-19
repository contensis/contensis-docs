1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

This endpoint requires the complete resource representation, including the version object, in the request body. Any property omitted will be considered for removal from the resource.

PUT/api/management/projects/**{projectId}**/contenttypes/**{contentTypeId}**

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

**contentTypeId***(required)*

path

string

\-

The content type identifier.

**contentType***(required)*

body

object

[content type](/help-and-docs/apis/management-http/content/content-types/content-types)

The complete content type resource

## Responses

HTTP status code

Reason

Model

**200**

Success

[Content type](/help-and-docs/apis/management-http/content/content-types/content-types)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Content type not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Not the latest version

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)