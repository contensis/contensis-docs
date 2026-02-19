1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

This endpoint publishes content types, ensuring that changes are reflected in both the user interface and frontend form renders.

POST/api/management/projects/**{projectId}**/contenttypes/**{contentTypeId}**/workflow/events

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

**trigger***(required)*

body

object

workflow trigger

Details to invoke the workflow event. You can target a language variation by specifying the language

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

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

JSON

```
{
    "language": "en-GB",
    "version": "2.1",
    "event": "publish"
}
```