1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [Groups](/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

DELETE/api/security/groups/**{groupIdentifier}**/groups/**{childGroupIdentifier}**

## Parameters

Name

Parameter type

Type

Format

Description

**groupIdentifier***(required)*

path

string

[group identifier](/help-and-docs/apis/management-http/security/user-and-group-identifiers)

For convenience, Group resources can be referenced by using either the group name or id

**childGroupIdentifier***(required)*

path

object

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

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Remove a child group by Id

HTTP

```
DELETE: /api/security/groups/6254736c-70e1-43b0-b769-f8e0f6359862/groups/3d063773-2ca9-4baf-90e1-ed674fa68640
```

Remove a child group from a named group by Id

HTTP

```
DELETE: /api/security/groups/Paper%20Street%20Soap%20Company/groups/3d063773-2ca9-4baf-90e1-ed674fa68640
```

Remove a named child group from a named group

HTTP

```
DELETE: /api/security/groups/Paper%20Street%20Soap%20Company/groups/Liposuction%20Technicians
```

Remove a named child group

json

```
DELETE: /api/security/groups/6254736c-70e1-43b0-b769-f8e0f6359862/groups/Liposuction%20Technicians
```

## Remarks

**Permissions**

Member of `System Administrators`.