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
-   [Validation](#validation)
-   [Example](#example)

The date range object represents a start and end point in time

## Properties

Name

Type

Format

Description

from

datetime

The date and time the range starts

to

datetime

The date and time the range ends

## Validation

The *from* value cannot be greater than the *to* value

## Example

JavaScript

```
const entry = await client.entries.get('<entry_id>');

console.log(entry.myDateRange.from);
console.log(entry.myDateRange.to);
```

## On this page

-   [Properties](#properties)
-   [Validation](#validation)
-   [Example](#example)