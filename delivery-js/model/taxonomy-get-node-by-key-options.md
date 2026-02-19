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

A structure that supports multiple configuration options for requesting taxonomy nodes

## Properties

Name

Type

Description

key

string

The taxonomy node key

order

string

Specifies the order of taxonomy nodes: 'defined' or 'alphabetical' (defaults to 'alphabetical')

childDepth

number

The depth of resolved children (defaults to 1)

language

string

The language code for the retrieved taxonomy nodes

## Example

TypeScript

```
const node = await client.taxonomy.getNodeByKey("0/1");

console.log(node);
```

TypeScript

```
const node = await client.taxonomy.getNodeByKey({
  key: "0/1",
  order: "defined",
  childDepth: 10,
  language: "fr-FR",
});

console.log(node);
```

## On this page

-   [Properties](#properties)
-   [Example](#example)