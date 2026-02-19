1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

The link object represents a reference to another entry or asset.

## Properties

Name

Type

Format

Description

sys

object

The link system data

sys.id

string

`Guid`

The identifier of the referenced entry or asset

sys.dataFormat

string

Either *entry* or *asset*

sys.language

string

[Language code](/help-and-docs/apis/management-js/key-concepts/localization)

The target language of the entry variation

## Remarks

When setting a link, the dataFormat property does not have to be set as it will be determined by the API service. If no language is specified then the project default language will be assumed.

## Example

JSON

```
{
    "sys": {
        "id": "3995f92c-2b3c-45bb-b2a6-1f1b6314be7a",
        "dataFormat": "entry",
        "language": "fr-FR"
    }
}
```