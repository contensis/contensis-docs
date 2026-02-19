1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Groups](https://www.contensis.com/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 20 June 2022

HEAD/api/security/groups/**{groupIdentifier}**/users/**{userIdentifier}**

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

Success - User in Group

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

User not in group

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Check if a user is a member of the a group by Id

HTTP

```
HEAD: /api/security/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251/users/9f02a3d1-d8eb-4b10-8ed6-293a11d5201f
```

Check if user 'tdurden' is a member of the 'Paper Street Soap Company' group by name

HTTP

```
HEAD: /api/security/groups/Paper%20Street%20Soap%20Company/users/tdurden
```

Check if user is a member of the 'Fight club' group by email address

HTTP

```
HEAD: /api/security/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251/users/tdurden@fightclub.com
```

## Remarks

Membership will be classed as true if the user is a member of a child group of the specified group.

**Permissions**

Member of `System Administrators` or the authenticated user matching the specified user can check group membership.