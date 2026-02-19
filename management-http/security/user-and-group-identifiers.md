## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 24 September 2024

For convenience, [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users) and [Group](https://www.contensis.com/help-and-docs/apis/management-http/security/groups) resources can be identified by using one of several identifiers.

For example, a [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users) can be identified by Username, Id or Email Address. A [Group](https://www.contensis.com/help-and-docs/apis/management-http/security/groups) can be identified by Name or Id.

A combination of identifiers can be used if an endpoint requires both types of resource.

## **Available User identifiers**

Identifier

Format

Description

Id

UUID

The user Id

Username

string

The user username

Email address

string

The user email in valid email format

## Available Group identifiers

Identifier

Format

Description

Id

Guid

The group Id

Name

string

The group name

## Example requests

### User requests

HTTP

```
GET: /api/security/users/82f73a9b-2a13-4d63-bcc1-e8ee5047b01
```

HTTP

```
GET: /api/security/users/t.durden
```

HTTP

```
GET: /api/security/users/t.durden@fightclub.com
```

### Group requests

HTTP

```
GET: /api/security/groups/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c
```

HTTP

```
GET: /api/security/groups/Paper%20Street%20Soap%20Company
```

### Combination requests

HTTP

```
HEAD: /api/security/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251/users/9f02a3d1-d8eb-4b10-8ed6-293a11d5201f
```

HTTP

```
HEAD: /api/security/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251/users/t.durden
```

HTTP

```
HEAD: /api/security/groups/9bb89380-fd49-41a5-ab2f-fc25e482a251/users/t.durden@fightclub.com
```

HTTP

```
HEAD: /api/security/groups/Paper%20Street%20Soap%20Company/users/3d063773-2ca9-4baf-90e1-ed674fa68640
```