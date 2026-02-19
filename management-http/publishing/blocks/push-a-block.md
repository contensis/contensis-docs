1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 January 2023

POST/api/management/projects/**{projectId}**/blocks?autoRelease=**{true|false}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**release**

query

boolean

Automatically release the block as soon as it has been discovered. Defaults to false.

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

Pushing a new version of the movie-listing block

JSON

```
Accept: application/json
POST: /api/management/projects/movieDb/blocks/

{
    "id": "movie-listing",
    "projectId": "movieDb",
    "image": {
        "uri": "moviedb/movie-listing",
        "tag": "81e13d08"
    },
    "source": {
        "branch": "master",
        "provider": "github",
        "repositoryUrl": "https://github.com/moviedb/movie-listing.git",
        "commit": {
            "id": "81e13d08",
            "message": "Implemented movie listing",
            "authorEmail": "m.scorsese@film.com",
            "committerEmail": "m.scorsese@film.com",
            "datetime": "2021-08-09T14:05:10Z"
        }        
    }
}
```

## Remarks

The resource used to push a block is a subset of the final [block version](https://developer.zengenti.com/contensis/api/management/http/v/beta/model/block-version.html) as the remaining properties (i.e. endpoints, static paths, etc...) are automatically 'discovered' by the publishing platform by inspecting the referenced docker image and extracting the details defined in the manifest file.