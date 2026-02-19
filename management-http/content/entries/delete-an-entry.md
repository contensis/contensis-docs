1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  [Entries](/help-and-docs/apis/management-http/content/entries)

[Log in to add to favourites](/account/login)

Page last updated 01 March 2023

DELETE/api/management/projects/**{projectId}**/entries/**{entryId}**?language=**{comma separated list of variations to delete}**&permanent=**{permanently delete}**

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

**language**

path

string\[...\]

language

A comma separated list of variations to delete

**permanent**

query

boolean

\-

Whether a deletion should be permanent (true) or to the recycle bin (false)

## Responses

HTTP status code

Reason

Model

**204**

Success

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

An example showing how to delete an entry and all it's language variations

HTTP

```
DELETE: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```

An example showing how to delete the French and German language variations of an entry

HTTP

```
DELETE: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c?language=fr,de
```

An example showing how to permanently delete the French and German language variations of an entry

HTTP

```
DELETE: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c?language=fr,de&permanent=true
```

## Remarks

You must be authorised to delete all the language variations or the whole request will fail.