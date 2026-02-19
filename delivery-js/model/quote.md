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

The quote object represents a section of referenced text from an external source.

## Properties

Name

Type

Format

Description

text

string

The quote text.

source

string

The source of the quote.

## Example

TypeScript

```
const entry = await client.entries.get("<entry-id>");

console.log(entry.myQuote.text);
console.log(entry.myQuote.source);
```

## On this page

-   [Properties](#properties)
-   [Example](#example)