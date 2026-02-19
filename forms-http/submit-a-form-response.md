1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Forms API](/help-and-docs/apis/forms-http)

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

This endpoint allows you to post a form response

POST/api/forms/projects/**{projectId}**/contenttypes/**{contentTypeId}**/languages/**{language}**/entries

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

**contentTypeId***(required)*

path

string

\-

The content type identifier.

**language***(required)*

path

string

language

The language property specifies the language variation of the form, or use \`default\` for the default language.

**formData***(required)*

body

object

\-

The user submitted form data collected from the rendered form

## Responses

HTTP status code

Reason

Model

**200**

Created

[Form response confirmation](/help-and-docs/apis/forms-http/form-response-confirmation)

**404**

Project not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Content type not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Language is invalid

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

An example of submitting a form response for a form containing name, emailAddress, mobile fields

cURL

```
curl --location --globoff 'https://cms-{alias}.cloud.contensis.com/api/forms/projects/{projectId}/contentTypes/{contentTypeId}/languages/{language}/entries' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
  "name": "Emily Dawson",
  "emailAddress": "emily.dawson@fictionalcorp.com",
  "mobile": "07123 987654"
}'
```