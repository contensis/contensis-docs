1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Entries](https://www.contensis.com/help-and-docs/apis/management-http/content/entries)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 December 2024

GET/api/management/projects/**{projectId}**/contenttypes/**{contentTypeId}**/entries

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

**versionStatus**

query

string

\-

The status of the associated entry, either published or latest. The default is published

**pageIndex**

query

number

integer

The index of the page.

**pageSize**

query

number

integer

The number of results per page. The default is 25.

**order**

query

string

\-

A comma-separated list of the field Ids to order the results by. Prefix field Id with - for descending order.

**language**

query

string

language

The specified language for the node. If no value is provided then the menu order is removed for all languages

## Responses

HTTP status code

Reason

Model

**200**

Success

[Entry](https://www.contensis.com/help-and-docs/apis/management-http/content/entries)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)