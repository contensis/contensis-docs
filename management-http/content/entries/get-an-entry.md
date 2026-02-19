1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  [Entries](/help-and-docs/apis/management-http/content/entries)

[Log in to add to favourites](/account/login)

Page last updated 08 November 2023

GET/api/management/projects/**{projectId}**/entries/**{entryId}**

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

**version**

query

string

\-

The version number of the resource. {major}.{minor} e.g. 1.2

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

[Entry](/help-and-docs/apis/management-http/content/entries)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Entry not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get an entry by id

HTTP

```
GET: /api/management/projects/movieDb/entries/movie/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```

## Remarks

If a specific versionNo value has been provided then the versionStatus value will be ignored.