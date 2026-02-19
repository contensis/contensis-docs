1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

A group resource contains references to users and child groups that form membership of the group.

## Properties

Name

Type

Format

Description

id

string

GUID

The group identifier as a 128 bit GUID.

name

string

The unique group name.

description

string

A description for the purpose of the group.

type

string

The type of group - 'sys', 'contensis', 'external'.

custom.\*

object

Custom string properties for the group.

created

datetime

The datetime the group was created.

modified

datetime

The datetime the group was last modified.

## Example

JSON

```
{
    "id": "236f1ce9-e5e6-4a93-b178-d52f2f723428",
    "name": "Paper Street Soap Company",
    "description": "Employees of the Paper Street Soap Company", 
    "type": "contensis",
    "custom" : {
        "clientId": "PSSC"
    },
    "created": "2020-01-31 15:26:54",
    "modified": "2020-01-31 15:27:00"    
}
```