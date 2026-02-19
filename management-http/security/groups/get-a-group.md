1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Groups](https://www.contensis.com/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 June 2022

GET/api/security/groups/**{groupIdentifier}**

## Parameter

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

## Responses

HTTP status code

Reason

Model

**200**

Success

[Group](https://www.contensis.com/help-and-docs/apis/management-http/security/groups)

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

Get a group by id

HTTP

```
GET: /api/security/groups/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```

Get a group by name

HTTP

```
GET: /api/security/groups/Paper%20Street%20Soap%20Company
```

## Remarks

**Permissions**

Member of `System Administrators`.