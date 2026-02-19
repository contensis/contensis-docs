1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

POST/api/management/projects/**{projectId}**/blocks/**{blockId}**/actions

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**blockId***(required)*

path

string

The block identifier

## Responses

HTTP status code

Reason

Model

**202**

Accepted

[Block version](/help-and-docs/apis/management-http/publishing/blocks/block-version)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Mark version 2 of the movie-listing block as broken

JSON

```
Accept: application/json
POST: /api/management/projects/movieDb/blocks/movie-listing/actions

{
    "type": "markAsBroken",
    "data": {
        "version": "2"
    }
}
```

## Remarks

Marking a block version as broken will disable it and ensure it can't be released