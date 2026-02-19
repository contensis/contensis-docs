1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  proxies

[Log in to add to favourites](/account/login)

Page last updated 25 June 2024

A proxy needs to be attached to a node in Site View to direct traffic from the incoming user request to its new destination.

PUT/api/management/projects/**{projectId}**/nodes/**{nodeId}**

## Parameters

Name

Parameter type

Type

Format

Description

**projectId***(required)*

path

string

\-

The project identifier found in the project overview screen of the management console.

**nodeId***(required)*

path

string

uuid

The node identifier as a 128 bit GUID

**node***(required)*

body

object

node

The node object to update

## Responses

HTTP status code

Reason

Model

**200**

Success

[Node](/help-and-docs/apis/management-http/navigation/nodes)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Node not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Attach a proxy to an existing node

HTTP

```
PUT: /api/management/projects/website/nodes/d6bdea41-729c-4a07-85bf-a392aa0afc2b

{
	"parentId": "bda31335-136c-42f4-bedc-69660b711a40",
	"displayName": {
		"en-GB": "Blood Meridian"
	},
	"slug": {
		"en-GB": "blood-meridian"
	},
	"proxy": {
		"id": "bcb62955-efa1-4e7f-93e3-757456fa24e4"
	},
}
```

Attach a proxy and enable partialMatching

HTTP

```
PUT: /api/management/projects/website/nodes/d6bdea41-729c-4a07-85bf-a392aa0afc2b

{
	"parentId": "bda31335-136c-42f4-bedc-69660b711a40",
	"displayName": {
		"en-GB": "Blood Meridian"
	},
	"slug": {
		"en-GB": "blood-meridian"
	},
	"proxy": {
		"id": "bcb62955-efa1-4e7f-93e3-757456fa24e4",
		"enablePartialMatching": true
	},
}
```

Detach a proxy from an existing node

HTTP

```
PUT: /api/management/projects/website/nodes/d6bdea41-729c-4a07-85bf-a392aa0afc2b

{
	"parentId": "bda31335-136c-42f4-bedc-69660b711a40",
	"displayName": {
		"en-GB": "Blood Meridian"
	},
	"slug": {
		"en-GB": "blood-meridian"
	},
	"proxy": null,
}
```