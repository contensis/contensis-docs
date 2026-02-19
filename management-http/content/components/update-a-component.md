1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Components](https://www.contensis.com/help-and-docs/apis/management-http/content/components)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 29 September 2021

PUT/api/management/projects/**{projectId}**/components/**{componentId}**

## Parameters

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

**componentId***(required)*

path

string

The component identifier.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Component](https://www.contensis.com/help-and-docs/apis/management-http/content/components)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Component not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

JSON

```
PUT: /api/management/projects/movieDb/components/movieRole
{
    "id": "movieRole",
    "projectId": "website",
    "name": {
        "en-GB": "Movie Role"
    },
    "description": {
        "en-GB": "A Persons role within a movie"
    },
    "fields": [
        {
            "id": "person",
            "name": {
            "en-GB": "Person"
            },
            "dataType": "object",
            "dataFormat": "entry",
            "description": {
                "en-GB": "The actor or crew member"
            },
            "default": {},
            "validations": {
                "allowedContentTypes": {
                    "contentTypes": ["person"]
                }
            },
            "editor": {
                "id": "entry",
                "instructions": {
                    "en-GB": ""
                },
                "properties": {
                    "placeholderText": {
                        "en-GB": ""
                    }
                }
            }
        },
        {
            "id": "role",
            "name": {
                "en-GB": "Role"
            },
            "dataType": "String",
            "dataFormat": null,
            "description": {},
            "default": {},
            "validations": null,
            "editor": null
        }
    ],
    "workflowId": "ContensisDefault",
    "dataFormat": "component",
 }
```