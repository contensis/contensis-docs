## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 02 July 2025

A Tag is a reusable resource that can be linked to one or more content or asset entries. The linking of tags to entries allows those entries to be grouped by and retrieved on the basis of how they have been tagged, helping you organise and classify content for easier filtering, searching, and reporting.

A Tag belongs to a single Tag group and a single entry can link multiple tags from a tag group via one or more Tag picker fields assigned to the Content Type.

Tags from multiple tag groups can be used by including a Tag picker field for each Tag group we wish to link tag(s) from.

## Properties

Name

Type

Description

id

`string`

The tag GUID identifier

groupId

`string`

The tag's parent tag group GUID identifier

value

`string`

A simple string representing the value of the tag

label

[`LocalizedString`](/help-and-docs/apis/management-js/key-concepts/localization)

Object containing a key for each language code supported by the project (minimum `primaryLanguage`) and the value of each key represents the localized label

usageCount

`number`

The number of places the tag is linked from

version

`VersionInfo`

The version object containing details of creation, modification and a `versionNo` in the format `"1.0"`

## Example

This example JSON shows a tag as it is retrieved from the Management API

JSON

```
{
  "groupId": "topics",
  "id": "109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c",
  "value": "books",
  "label": {
    "en-GB": "Books",
    "cy": "Llyfrau",
    "fr-FR": "Livre"
  },
  "version": {
    "versionNo": "1.0",
    "created": "2025-06-25T14:09:59.877Z",
    "createdBy": "zengenti",
    "modified": "2025-06-25T14:09:59.877Z",
    "modifiedBy": "zengenti"
  },
  "usageCount": 0
}
```