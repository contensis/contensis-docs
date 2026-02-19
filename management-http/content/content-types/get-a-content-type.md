1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

This endpoint retrieves the details of a specific content type, such as an entry, asset, or form based on a given data format.

GET/api/management/projects/**{projectId}**/contenttypes/**{contentTypeId}**

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

**versionStatus**

query

string

The status of the associated entry, either published or latest. The default is published

**version**

query

string

The version number of the resource. {major}.{minor} e.g. 1.2

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

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)