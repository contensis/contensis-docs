## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 10 December 2020

## Properties

Name

Type

Format

Description

**id**

string

\-

The group identifier as a 128 bit GUID.

**name**

string

\-

The unique group name

**description**

string

\-

A description for the purpose of the group.

**type**

string

\-

The type of group - 'sys', 'contensis', 'external'.

**userCount**

integer

integer

The count of users in the group

**childGroupCount**

integer

integer

The count of child groups in the group

**custom.\***

object

\-

Custom string properties for the group.

## Example

JSON

```
{
    "id": "236f1ce9-e5e6-4a93-b178-d52f2f723428",
    "name": "Paper Street Soap Company",
    "description": "Employees of the Paper Street Soap Company", 
    "type": "contensis",
    "userCount": 2,
    "childGroupCount": 0,
    "custom" : {
        "clientId": "PSSC"
    }
}
```