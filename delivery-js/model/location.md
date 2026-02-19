## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 13 November 2024

## On this page

-   [Properties](#properties)
-   [Example](#example)

The location object represents a geographical coordinate that specifies the position of a point on the Earth's surface.

## Properties

Name

Type

Format

Description

lat

number

The north-south position.

lon

number

The east-west position.

## Example

Get an entry by its ID and output properties from a location field in the entry called 'myLocation'

TypeScript

```
const entry = await client.entries.get("<entry-id>");

console.log(entry.myLocation.lat);
console.log(entry.myLocation.lon);
```

## On this page

-   [Properties](#properties)
-   [Example](#example)