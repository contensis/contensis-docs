1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## On this page

-   [Properties](#properties)
-   [Example](#example)

The composed field type contains the data that the [composer editor](https://www.contensis.com/help-and-docs/user-guides/content-modelling/field-editors/composer-field) defines. It is an array of objects which expose *type* and *value* properties. The *type* property is a name given to an *allowed field type validation* defined in the [content type](https://www.contensis.com/help-and-docs/apis/delivery-js/model/content-type) that the entry is based on. The *value* contains the data for the field.

An *allowed field type* is essentially any standard field (such as Image, Heading, Location, etc.) that restricts what types of field can be added to a composed field.

For example, an *allowed field* could be defined with a type of *Heading* and named mainHeading or with a type of *Image* and named bannerImage. There can be multiple *allowed fields* based on the same type, but a composed field cannot contain other composed fields.

## Properties

Name

Type

Format

Description

type

string

The field name given to a field type defined in the content type

value

*Any*

*Any*

The value of the field, which can be of any type

## Example

Get and output a composed field called myComposedField from a specific entry

TypeScript

```
const entry = await client.entries.get("<entry-id>");

for (const field of entry.myComposedField) {
  switch (field.type) {
    case "heading":
      console.log(field.value);
    case "markup":
      console.log(field.value);
    case "image":
      console.log(field.value.asset.sys.uri, field.value.altText);
    case "quote":
      console.log(field.value.text, field.value.source);
    default:
      break;
  }
}
```

## On this page

-   [Properties](#properties)
-   [Example](#example)