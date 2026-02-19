1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Groups](https://www.contensis.com/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 14 June 2024

GET/api/security/groups/**{groupIdentifier}**/groups?order=**{order}**&pageIndex=**{pageIndex}**&pageSize=**{pageSize}**&includeInherited=**{includeInherited}**&zenQL=**{zenQL}**&excludedGroups=**{excludedGroups}**&includeSelf=**{includeSelf}**

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

**includeInherited**

query

boolean

\-

Set to true in order to return the direct child groups and ALL the descendant groups

**zenql**

query

string

\-

ZenQL query to select the groups returned in the listing

**excludedGroups**

query

string

\-

A comma-separated list of group identifiers such as Guid ids or names whose children will be excluded from the returned values

**includeSelf**

query

boolean

\-

Whether to include the group for which children are being requested in the returned groups

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

Get child groups for a group by Id

HTTP

```
GET: /api/security/groups/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/groups
```

Get child groups for a group by name

HTTP

```
GET: /api/security/groups/Paper%20Street%20Soap%20Company/groups
```

Get the first page of child groups and ALL descendant groups for a group, with page sizes of 10

HTTP

```
GET: /api/security/groups/Paper%20Street%20Soap%20Company/groups?pageIndex=0&pageSize=10&includeInherited=true
```

Get the first page of child groups and ALL descendant groups for a group, including the parent group, but only if they were created in the last seven days and excluding certain groups

HTTP

```
GET: /api/security/groups/Paper%20Street%20Soap%20Company/groups?includeInherited=true&zenQL=created>now(-7)&excludedGroups=0617b0ac-4dda-4279-b070-5930511c86e0,37394083-ff04-4ecb-b8ac-1f6e7a26c875&includeSelf=true
```

## Remarks

**Permissions**

Member of `System Administrators`.