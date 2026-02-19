1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Renderers

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

POST/api/management/projects/**{projectId}**/renderers/

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

**200**

Success

[Renderer](/help-and-docs/apis/management-http/publishing/renderers/renderer)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Create a renderer to render all entries of type movie

HTTP

```
{
	"id": "movie-record",
	"name": "Movie record page",
	"description": "Used to render the movie record page",
	"assignedContentTypes": [
		"movie"
	],
	"rules": [
		{
			"return": {
				"blockId": "movie-record",
				"endpointId": null
			}
		}
	]
}
```

Create a renderer to be assigned to a site view node

HTTP

```
{
    "id": "movie-record",
    "name": "Movie record page",
    "description": "Used to render the movie record page",
    "rules": [
        {
            "return": {
                "blockId": "movie-record",
                "endpointId": null
            }
        }
    ]
}
```