1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  [Entries](/help-and-docs/apis/management-http/content/entries)

[Log in to add to favourites](/account/login)

Page last updated 08 November 2023

POST/api/management/projects/**{projectId}**/entries/**{entryId}**/workflow/events

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

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
POST: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c/workflow/events

{
    "language": "en-GB",
    "event": "*.sysUnpublish"
}
```