## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content

[Log in to add to favourites](/account/login)

Page last updated 16 July 2020

## Properties

Name

Type

Format

Description

**id**

string

\-

A unique field identifier

**name**

object

localized value

A friendly name for the field

**description**

object

localized value

The description for the field's purpose

**dataType**

string

dataType

The field data type

**dataFormat**

string

dataFormat

The field data format

**default**

object

localized value

The default value for the field if no value is provided by an author

**validations**

object

\-

The validations that will be performed on the field when the entry is either created or updated

**editor**

object

editor

Configuration for the Contensis entry field editor

**groupId**

string

\-

The identifier of the group (defined in the content type groups property) that the field belongs to. Enables related fields to be grouped together in the UI

## Example

JSON

```
{
      "id": "title",
      "name": {
        "en-GB": "Title"
      },
      "dataType": "String",
      "dataFormat": null,
      "description": {},
      "default": {},
      "validations": null,
      "editor": {
        "id": "text",
        "instructions": {
          "en-GB": "The title of the movie"
        },
        "properties": {
          "placeholderText": {
            "en-GB": "Enter the full title of the movie appropriate to the region"
          }
        },
        "groupId": "summary"
      }
    }
```

JSON

```
{
      "id": "title",
      "name": {
        "en-GB": "Title"
      },
      "dataType": "String",
      "dataFormat": null,
      "description": {},
      "default": {},
      "validations": null,
      "editor": {
        "id": "text",
        "instructions": {
          "en-GB": "The title of the movie"
        },
        "properties": {
          "placeholderText": {
            "en-GB": "Enter the full title of the movie appropriate to the region"
          }
        },
        "groupId": "summary"
      }
    }
```

JSON

```
{
      "id": "title",
      "name": {
        "en-GB": "Title"
      },
      "dataType": "String",
      "dataFormat": null,
      "description": {},
      "default": {},
      "validations": null,
      "editor": {
        "id": "text",
        "instructions": {
          "en-GB": "The title of the movie"
        },
        "properties": {
          "placeholderText": {
            "en-GB": "Enter the full title of the movie appropriate to the region"
          }
        },
        "groupId": "summary"
      }
    }
```