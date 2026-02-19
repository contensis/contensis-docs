1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

This endpoint deletes a content type from a specific project. Once deleted, the content type is permanently removed and cannot be retrieved, as it is not moved to the recycle bin.

DELETE/api/management/projects/**{projectId}**/contenttypes/**{contentTypeId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**contentTypeId***(required)*

path

string

The content type identifier.

## Responses

HTTP status code

Reason

Model

**204**

Success

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Content type not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

An example of deleting a content type called enquiryForm from the website project

cURL

```
curl --location --request DELETE 'https://cms-{alias}.cloud.contensis.com/api/management/projects/website/contenttypes/enquiryform' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {token}'
```