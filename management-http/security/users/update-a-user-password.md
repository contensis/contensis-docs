1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 June 2022

POST/api/security/users/**{userIdentifier}**/credentials/password

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

**200**

OK - password updated successfully

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

Invalid existing password

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Password invalid

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

JSON

```
POST: /api/security/users/9bb89380-fd49-41a5-ab2f-fc25e482a251/credentials/password
{
    "existing": "m4rl451ng3r",
    "new": "pr0j3ctM4yh3m"
}
```

JSON

```
POST: /api/security/users/t.durden/credentials/password
{
    "existing": "m4rl451ng3r",
    "new": "pr0j3ctM4yh3m"
}
```

Example request for a System Adminstrator member

JSON

```
POST: /api/security/users/9bb89380-fd49-41a5-ab2f-fc25e482a251/credentials/password
{
    "new": "pr0j3ctM4yh3m"
}
```

JavaScript

```
POST: /api/security/users/t.durden@fightclub.com/credentials/password
{
    "new": "pr0j3ctM4yh3m"
}
```

## Remarks

If the existing password is wrong then a 409 Conflict status is returned. If the new password does not meet the [user password policy](https://www.contensis.com/help-and-docs/apis/management-http/security/user-password-policy "user password policy") then a 422 Unprocessable Entity status is returned.