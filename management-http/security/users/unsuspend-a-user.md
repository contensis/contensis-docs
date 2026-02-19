1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 29 March 2023

POST/api/security/users/**{userIdentifier}**/actions/

## Parameter

Name

Parameter type

Type

Format

Description

**UserIdentifier***(required)*

path

string

[user identifier](https://www.contensis.com/help-and-docs/apis/management-http/security/user-and-group-identifiers)

For convenience, User resources can be referenced by using one of several identifiers - username, email address or Id.

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

User not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Unsuspend a user

HTTP

```
POST: /api/security/users/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/actions/
{
    "type": "unsuspend"
}
```

## Remarks

**Permissions**

Member of `System Administrators`.