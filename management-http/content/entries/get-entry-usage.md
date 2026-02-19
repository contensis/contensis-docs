1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Entries](https://www.contensis.com/help-and-docs/apis/management-http/content/entries)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 22 June 2020

GET/api/management/projects/**{projectId}**/entries/**{entryId}**/usage

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

**entryId***(required)*

query

string

uuid

The entry identifier as a 128 bit GUID

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

[Entry usage info](https://www.contensis.com/help-and-docs/apis/management-http/content/entries/entry-usage-info)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Entry not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c/usage
```