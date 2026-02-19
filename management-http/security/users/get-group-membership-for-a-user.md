1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [User](/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

GET/api/security/users/**{userIdentifier}**/groups

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

**order**

query

string

\-

A comma-separated list of the field Ids to order the results by. Prefix field Id with - for descending order.

**pageIndex**

query

number

integer

The index of the page.

**pageSize**

query

number

integer

The number of results per page. The default is 25.

**includeInherited***(required)*

query

boolean

\-

A flag to determine whether groups a user is implicitly a member of by child groups relationships should also be returned. The default is false.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Group](/help-and-docs/apis/management-http/security/groups)

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

HTTP

```
GET: /api/security/users/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/groups?includeInherited=true
```

HTTP

```
GET: /api/security/users/tdurden/groups?includeInherited=true
```

HTTP

```
GET: /api/security/users/t.durden@fightclub.com/groups?includeInherited=true
```

## Remarks

**Permissions**

Members of `System Administrators` are permitted to get the groups for any user.

Authenticated standard user accounts are permitted to get their own groups.