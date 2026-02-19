[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

A component determines a reusable schema added to [content types](/help-and-docs/apis/management-js/model/content-type) which [entries](/help-and-docs/apis/management-js/model/entry) are then created from. Components contain a list of fields just like content types, and allow for a standardized schema for modelling content.

## Properties

Name

Type

Format

Description

id

string

A unique component identifier

projectId

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console

name

object

[Localized value](/help-and-docs/apis/management-js/key-concepts/localization)

The friendly name given to a component

description

object

[Localized value](/help-and-docs/apis/management-js/key-concepts/localization)

The description text given to a component

fields

object \[…\]

[Field](#field)

A collection of fields that form the schema for an entry

workflowId

string

The workflow process that derived entries will follow.

dataFormat

string

Either *entry* or *asset*

version

object

[Version](/help-and-docs/apis/management-js/model/version)

Version information about the component

## Field

The field object is the definition of a field within an entry. The field also contains the validations and editor configuration that is used within the Contensis UI and services.

### Properties

Name

Type

Format

Description

id

string

A unique field identifier

name

object

[Localized value](/help-and-docs/apis/management-js/key-concepts/localization)

A friendly name for the field

description

object

[Localized value](/help-and-docs/apis/management-js/key-concepts/localization)

The description for the field's purpose

dataType

string

[Data type](/help-and-docs/apis/management-js/key-concepts/data-types)

The field data type

dataFormat

string

[Data type](/help-and-docs/apis/management-js/key-concepts/data-formats)

The field data format

default

object

[Localized value](/help-and-docs/apis/management-js/key-concepts/localization)

The default value for the field if no value is provided by an editor

validations

object

The validations that will be performed on the field when the entry is either created or updated

editor

object

Editor

Configuration for the Contensis entry editor

## Localized value

A localized value is an object that has values that are keyed by [language codes](/help-and-docs/apis/management-js/key-concepts/localization) which allows multilingual variations of a specific property.

## Example

JSON

```
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
  "version": {
        "createdBy": "s.derrickson",
        "created": "2016-10-12T09:29:18.5144641+01:00",
        "modifiedBy": "b.cumberbatch",
        "modified": "2016-10-13T10:15:12.1973648+01:00",
        "publishedBy": "b.cumberbatch",
        "published": "2016-10-13T10:15:12.1973648+01:00",
        "versionNo": "2.0"
    }
}
```