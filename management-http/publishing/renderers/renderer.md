1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Renderers

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

## Properties

Name

Type

Format

Description

Example

**uuid**

string

uuid

The renderer identifier as a 128 bit GUID

**id**

string

\-

A unique renderer identifier

movie-listing

**projectId**

string

\-

The project identifier found in the project overview screen of the management console

movieDb

**name**

string

\-

The friendly name given to a renderer

**description**

string

\-

The description text given to a renderer

**assignedContentTypes**

string\[...\]

\-

An array of content type Id's associated with the renderer

movie, actor, studio

**rules**

object\[...\]

\-

Currently we support a single rule with a specified blockId. In the future we will extend rules to support multiple block and endpoint combinations based on different criteria.

**version**

object

[version](/help-and-docs/apis/management-http/content/version)

Version information about the renderer

## Example

HTTP

```
{
	"uuid": "f8e9989a-3db7-45d3-8b11-b447afe2d401",
	"id": "top-movie-listing",
	"projectId": "movieDb",
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
		"createdBy": "CI block push",
		"created": "2023-01-12T15:41:07.88043Z",
		"modifiedBy": null,
		"modified": null,
		"publishedBy": "CI block push",
		"published": "2023-01-12T15:41:07.88043Z",
		"versionNo": "1.0"
	}
}
```

HTTP

```
{
	"uuid": "f8e9989a-3db7-45d3-8b11-b447afe2d401",
	"id": "top-movie-listing",
	"projectId": "movieDb",
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
		"createdBy": "CI block push",
		"created": "2023-01-12T15:41:07.88043Z",
		"modifiedBy": null,
		"modified": null,
		"publishedBy": "CI block push",
		"published": "2023-01-12T15:41:07.88043Z",
		"versionNo": "1.0"
	}
}
```