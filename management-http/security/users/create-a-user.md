1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 June 2022

POST/api/security/users

## Parameter

Name

Parameter type

Type

Format

Description

**user***(required)*

body

object

[user](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

The user to create

## Responses

HTTP status code

Reason

Model

**201**

Created

[User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

User not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Request to create a user

JSON

```
POST: /api/security/users
{
    "username": "tdurden",
    "email": "t.turden@fightclub.com",
    "firstName": "Tyler",
    "lastName": "Durden",
    "timezone": "America/New_York",
    "expiry": "2050-12-31T23:59:59.999Z",
    "language": "en-US",
    "custom": {
        "department": "Soap sales"
    },
    "credentials": {
        "password": "pr0j3ctM4yh3m"
    }
}
```

Request to create a user with an initial status of suspended

JSON

```
POST: /api/security/users?suspended=true
{
    "username": "tdurden",
    "email": "t.turden@fightclub.com",
    "firstName": "Tyler",
    "lastName": "Durden",
    "timezone": "America/New_York",
    "expiry": "2050-12-31T23:59:59.999Z",
    "language": "en-US",
    "custom": {
        "department": "Soap sales"
    },
    "credentials": {
        "password": "pr0j3ctM4yh3m"
    }
}
```

Request to create a user with an initial status of password reset required

JSON

```
POST: /api/security/users?forcePasswordReset=true
{
    "username": "tdurden",
    "email": "t.turden@fightclub.com",
    "firstName": "Tyler",
    "lastName": "Durden",
    "timezone": "America/New_York",
    "expiry": "2050-12-31T23:59:59.999Z",
    "language": "en-US",
    "custom": {
        "department": "Soap sales"
    },
    "credentials": {
        "password": "pr0j3ctM4yh3m"
    }
}
```

## Remarks

If a username is not provided then the email will be used as the username.

Expiry must be a future date.  If an expiry date is not provided then no value will be set on the user and the user account will never expire.

Passwords must comply with the [user password policy](https://www.contensis.com/help-and-docs/apis/management-http/security/user-password-policy "user password policy").

**Permissions**

Member of `System Administrators`.