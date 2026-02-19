1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [User](/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

HEAD/api/security/users/**{userIdentifier}**/groups/**{groupIdentifier}**\[ ,...n \]

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

Success - User in Group

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

User not in group

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Single GroupId

HTTP

```
HEAD: /api/security/users/9f02a3d1-d8eb-4b10-8ed6-293a11d5201f/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251
```

HTTP

```
HEAD: /api/security/users/tdurden/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251
```

HTTP

```
HEAD: /api/security/users/t.durden@fightclub.com/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251
```

HTTP

```
HEAD: /api/security/users/t.durden@fightclub.com/groups/Paper%20Street%20Soap%20Company
```

Csv of GroupId Values

HTTP

```
HEAD: /api/security/users/653aca45-d768-48d4-9af0-435e138b063f/groups/0ccf6d37-56a2-4a0d-bda1-efc377369232,eee2ca1a-8736-48b7-a274-da6f35499e56,504f21d0-361c-4c56-a87c-25e24ea81dfc
```

HTTP

```
HEAD: /api/security/users/tdurden/groups/0ccf6d37-56a2-4a0d-bda1-efc377369232,eee2ca1a-8736-48b7-a274-da6f35499e56,504f21d0-361c-4c56-a87c-25e24ea81dfc
```

HTTP

```
HEAD: /api/security/users/tdurden/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251
```

HTTP

```
HEAD: /api/security/users/t.durden@fightclub.com/groups/Paper%20Street%20Soap%20Company,Liposuction%20Technicians
```

HTTP

```
HEAD: /api/security/users/t.durden@fightclub.com/groups/0ccf6d37-56a2-4a0d-bda1-efc377369232,Liposuction%20Technicians
```

## Remarks

Membership will be classed as true if the user is a member of a child group of the specified group. Multiple groupId values can be passed in the path as comma-separated-value (CSV). If a CSV is passed then an OR evaluation will be performed.

**Permissions**

Member of `System Administrators`.