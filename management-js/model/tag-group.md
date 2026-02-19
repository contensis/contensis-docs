## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 02 July 2025

Tag groups organise related tags under a shared category, making your tagging system easier to manage. A Tag group represents a distinct collection of tags that can be assigned to one or more content type or component fields.

## Properties

Name

Type

Description

id

`string`

The tag group identifier

name

`string`

The name of the tag group

description

`string`

A short description of the tag group

tagCount

`number`

The number of tags that exist in this tag group

version

`VersionInfo`

The version object containing details of creation, modification and a `versionNo` in the format `"1.0"`

## Example

This example JSON shows a tag group as it is retrieved from the Management API

JSON

```
{
  "id": "topics",
  "name": "Topics",
  "description": "A collection of topic tags",
  "version": {
    "versionNo": "1.0",
    "created": "2025-06-25T13:06:46.273Z",
    "createdBy": "zengenti",
    "modified": "2025-06-25T13:06:46.273Z",
    "modifiedBy": "zengenti"
  },
  "tagCount": 5
}
```