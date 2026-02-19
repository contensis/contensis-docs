1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Groups](https://www.contensis.com/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 June 2022

POST/api/security/groups/**{groupIdentifier}**/users/

## Parameters

Name

Parameter type

Type

Format

Description

**groupIdentifier***(required)*

path

string

[group identifier](https://www.contensis.com/help-and-docs/apis/management-http/security/user-and-group-identifiers)

For convenience, Group resources can be referenced by using either the group name or id

**userIds***(required)*

body

string\[...\]

uuid

array of user UUIDs

## Responses

HTTP status code

Reason

Model

**204**

Success

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Group not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Add many users to a group in a single request

JSON

```
POST: /api/security/groups/6254736c-70e1-43b0-b769-f8e0f6359862/users/
[
    "75490b0f-56f7-4690-a20a-6f2a822f1d3f",
    "20b5e923-beb8-44ab-8bb4-34467582230f",
    "13f8cd48-7765-47b7-9fa3-2ad9c935a4be",
    "3c3d98a1-c80a-49d1-b602-f38ad2b01af8",
    "11f5ce76-ca86-45d8-9928-d7fd56863ec7"
]
```

JSON

```
POST: /api/security/groups/Paper%20Street%20Soap%20Company/users/
[
    "75490b0f-56f7-4690-a20a-6f2a822f1d3f",
    "20b5e923-beb8-44ab-8bb4-34467582230f",
    "13f8cd48-7765-47b7-9fa3-2ad9c935a4be",
    "3c3d98a1-c80a-49d1-b602-f38ad2b01af8",
    "11f5ce76-ca86-45d8-9928-d7fd56863ec7"
]
```

## Remarks

**Permissions**

Member of `System Administrators`.