1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](https://www.contensis.com/account/login)

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

[content type](https://www.contensis.com/help-and-docs/apis/management-http/content/content-types/content-types)

The complete content type resource

## Responses

HTTP status code

Reason

Model

**200**

Success

[Content type](https://www.contensis.com/help-and-docs/apis/management-http/content/content-types/content-types)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Content type not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Not the latest version

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)