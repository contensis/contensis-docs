1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Projects](/help-and-docs/apis/management-http/projects)

[Log in to add to favourites](/account/login)

Page last updated 05 August 2021

POST/api/management/projects/

## Parameter

Name

Parameter type

Type

Format

Description

**Project***(required)*

body

object

project

The project object to be created

## Responses

HTTP status code

Reason

Model

**201**

Created

[Project](/help-and-docs/apis/management-http/projects)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

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

JSON

```
POST: /api/management/projects/

{
    "id": "movieDb",
    "name": "Movie database",
    "description": "A source of movie and TV series",
    "primaryLanguage": "en-GB",
    "supportedLanguages": [
        "fr-FR",
        "de-DE"
    ]
}
```

## Remarks

If the *primaryLanguage* value is not included in the *supportedLanguages* array then it will automatically be added by the service when the project is created.