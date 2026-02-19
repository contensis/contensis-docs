1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 January 2023

POST/api/management/projects/**{projectId}**/blocks/**{blockId}**/actions

## Parameter

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

## Responses

HTTP status code

Reason

Model

**202**

Accepted

[Block version](https://www.contensis.com/help-and-docs/apis/management-http/publishing/blocks/block-version)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Rollback version 2 to the last live version

JSON

```
Accept: application/json
POST: /api/management/projects/movieDb/blocks/movie-listing/actions

{
    "type": "rollback",
    "data": { 
        "version": "2"
    }
}
```

## Remarks

Only actively live versions of a block can be rolled back.