## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## On this page

-   [Properties](#properties)
-   [Example](#example)

An image type is a container of an image asset with an associated caption.

## Properties

Name

Type

Format

Description

asset

object

[Asset](https://www.contensis.com/help-and-docs/apis/delivery-js/model/asset)

The asset that is linked to from the entry.

caption

string

The image caption, defined in the entry.

## Example

Get an entry resolving all fields to a link depth of 1 and output properties of the resolved 'thumbnailImage' field

TypeScript

```
const entry = await client.entries.get({
  id: "<entry-id>",
  linkDepth: 1,
});

console.log(entry.thumbnailImage.asset.sys.uri);
console.log(entry.thumbnailImage.altText);
// A linkDepth of 1 is required to resolve the extended asset.sys fields
console.log(entry.thumbnailImage.asset.sys.properties.width);
console.log(entry.thumbnailImage.asset.sys.properties.height);
```

## On this page

-   [Properties](#properties)
-   [Example](#example)