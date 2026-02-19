1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Groups](https://www.contensis.com/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 14 June 2024

GET/api/security/groups/**{groupIdentifier}**/users?order=**{order}**&pageIndex=**{pageIndex}**&pageSize=**{pageSize}**&includeInherited=**{includeInherited}**&zenQL=**{zenQL}**&excludedGroups=**{excludedGroups}**

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

**order**

query

string

\-

A comma-separated list of the field Ids to order the results by. Prefix field Id with - for descending order.

**pageSize**

query

number

integer

The number of results per page. The default is 25.

**pageIndex**

query

number

integer

The index of the page.

**includeInherited**

query

boolean

\-

Specify to include the users of all the descendant groups

**zenql**

query

string

\-

ZenQL query to select the users returned in the listing

**excludedGroups**

query

string

\-

A comma-separated list of group identifiers such as Guid ids or names whose children will be excluded from the returned values

## Responses

HTTP status code

Reason

Model

**200**

Success

[User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

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

Get users in a group by Id

HTTP

```
GET: /api/security/groups/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/users
```

Get users in a named group

HTTP

```
GET: /api/security/groups/Paper%20Street%20Soap%20Company/users
```

Get the first page of users in a group and all the group's descendant groups, with page sizes of 10

HTTP

```
GET: /api/security/groups/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/users?pageIndex=0&pageSize=10&includeInherited=true
```

Get the first page of users in a group and all the group's descendant groups where the user's firstname contains 'test' and where their membership does not descend from the 'System Administrators' group.

HTTP

```
GET: /api/security/groups/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/users?includeInherited=true&zenQL=firstname~test&excludedGroups=System%20Administrators
```

## Remarks

**Permissions**

Member of `System Administrators`.