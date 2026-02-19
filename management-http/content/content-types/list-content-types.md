1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

This endpoint lists all content types and allows filtering by data format and version status.

GET/api/management/projects/**{projectId}**/contenttypes/

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**versionStatus**

query

string

The status of the associated entry, either published or latest. The default is published

**dataFormat**

query

string

The specific dataFormat, default is all.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Content type](/help-and-docs/apis/management-http/content/content-types/content-types)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Retrieve all latest content types that produce entries

cURL

```
curl --location 'https://cms-{alias}.cloud.contensis.com/api/management/projects/{projectId}/contenttypes?versionstatus=latest&dataformat=form' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {token}'
```

Retrieve all published content types that produce from responses

cURL

```
curl --location 'https://cms-{alias}.cloud.contensis.com/api/management/projects/{projectId}/contenttypes?dataformat=form' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {token}'
```