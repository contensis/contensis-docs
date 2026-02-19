1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Projects](/help-and-docs/apis/management-http/projects)

[Log in to add to favourites](/account/login)

Page last updated 05 August 2021

PUT/api/management/projects/**{projectId}**

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

[Project](/help-and-docs/apis/management-http/projects)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

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

Update a project

JSON

```
PUT: /api/management/projects/movieDb
{
    "id": "movieDb",
    "name": "Movie database",
    "description": null,
    "primaryLanguage": "en-GB",
    "supportedLanguages": [
        "fr-FR",
        "de-DE"
    ],
     "color": "red"     
}
```

## Remarks

It is not possible to update the Id once you've created a project.