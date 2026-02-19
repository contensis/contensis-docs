1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Renderers

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

PUT/api/management/projects/**{projectId}**/renderers/**{rendererId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**rendererId***(required)*

path

string

The renderer identifier

## Responses

HTTP status code

Reason

Model

**200**

Success

[Renderer](/help-and-docs/apis/management-http/publishing/renderers/renderer)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Renderer not found

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
PUT: /api/management/projects/movieDb/contenttypes/top-movie-listing

{
	"name": "Latest top 10 movies",
	"description": "Renders the latest top 10 movies ordered by release date",
	"assignedContentTypes": ["landingPage"],
	"rules": [
		{
			"return": {
				"blockId": "movie-listing",
				"endpointId": null
			}
		}
	],
	"version": {
		"versionNo": "2.0"
	}
}
```