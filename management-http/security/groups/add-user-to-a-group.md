1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [Groups](/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

PUT/api/security/groups/**{groupIdentifier}**/users/**{userIdentifier}**

## Parameters

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

**groupIdentifier***(required)*

path

string

[group identifier](/help-and-docs/apis/management-http/security/user-and-group-identifiers)

For convenience, Group resources can be referenced by using either the group name or id

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

Group not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

User not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Add a user to a group by Ids

HTTP

```
PUT: /api/security/groups/6254736c-70e1-43b0-b769-f8e0f6359862/users/3d063773-2ca9-4baf-90e1-ed674fa68640
```

Add a user to a named group

HTTP

```
PUT: /api/security/groups/Paper%20Street%20Soap%20Company/users/3d063773-2ca9-4baf-90e1-ed674fa68640
```

Add a user to a group by username

HTTP

```
PUT: /api/security/groups/6254736c-70e1-43b0-b769-f8e0f6359862/users/tdurden
```

Add a user to a group by email

HTTP

```
PUT: /api/security/groups/6254736c-70e1-43b0-b769-f8e0f6359862/users/t.durden@fightclub.com
```

## Remarks

**Permissions**

Member of `System Administrators`.