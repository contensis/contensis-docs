1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [User](/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

DELETE/api/security/users/**{userIdentifier}**

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

**204**

Success

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

Delete a user by user id

HTTP

```
DELETE: /api/security/users/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```

Delete a user by username

HTTP

```
DELETE: /api/security/users/tdurden
```

Delete a user by email

HTTP

```
DELETE: /api/security/users/t.durden@fightclub.com
```

## Remarks

**Permissions**

Member of `System Administrators` are permitted to delete any other user account.

Authenticated Standard User accounts are permitted to delete their own account.