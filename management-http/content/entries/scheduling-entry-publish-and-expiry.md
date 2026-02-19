1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Entries](https://www.contensis.com/help-and-docs/apis/management-http/content/entries)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 11 October 2021

PUT/api/management/projects/**{projectId}**/entries/**{entryId}**/schedules/**{scheduleType}**?language=**{language}**

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

## Responses

HTTP status code

Reason

Model

**201**

Created

[Entry](https://www.contensis.com/help-and-docs/apis/management-http/content/entries)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Entry not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Scheduling an entry to publish in the future

JSON

```
PUT: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c/schedules/publish?language=en-gb

{
    "dateTime" : "2022-06-24T00:00:00Z"
}
```

Scheduling an entry to unpublish

JSON

```
PUT: /api/management/projects/movieDb/entries/71f73a9b-2a13-4d63-bcc1-e8ee5047b01c/schedules/unpublish?language=en-gb

{
    "dateTime" : "2023-06-24T00:00:00Z"
}
```