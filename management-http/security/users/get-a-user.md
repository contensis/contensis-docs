1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [User](/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

GET/api/security/users/**{userIdentifier}**

## Parameter

Name

Parameter type

Type

Format

Description

**UserIdentifier***(required)*

path

string

[user identifier](/help-and-docs/apis/management-http/security/user-and-group-identifiers)

For convenience, User resources can be referenced by using one of several identifiers - username, email address or Id.

## Responses

HTTP status code

Reason

Model

**200**

Success

[User](/help-and-docs/apis/management-http/security/users)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

User not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get a user resource by their UUID

HTTP

```
GET: /api/security/users/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```

Get a user resource by their username

HTTP

```
GET: /api/security/users/t.durden
```

Get a user resource by their email

HTTP

```
GET: /api/security/users/t.durden@fightclub.com
```

## Remarks

**Permissions**

Members of `System Administrators` are permitted to get any user.

Authenticated standard user accounts are permitted to get their own user.