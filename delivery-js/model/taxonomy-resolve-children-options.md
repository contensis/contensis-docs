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

A structure that supports multiple configuration options for resolving taxonomy nodes

## Properties

Name

Type

Description

key

string

The taxonomy node key.

node

[TaxonomyNode](/help-and-docs/apis/delivery-js/model/taxonomy-node)

The taxonomy node.

order

string

Specifies the order of taxonomy nodes: 'defined' or 'alphabetical' (defaults to 'alphabetical').

childDepth

number

The depth of resolved children (defaults to 1).

language

string

The language code for the retrieved taxonomy nodes.

## Example

TypeScript

```
const node = await client.taxonomy.resolveChildren("0/1");

console.log("Taxonomy resolveChildren with taxonomy node key:");
console.log(node);
```

TypeScript

```
const node = await client.taxonomy.resolveChildren({
  key: "0/1",
  name: "",
  path: "",
  hasChildren: true,
});

console.log("Taxonomy resolveChildren with taxonomy node:");
console.log(node);
```

TypeScript

```
const node = await client.taxonomy.resolveChildren({
  key: "0/1",
  order: "defined",
  childDepth: 10,
  language: "fr-FR",
});
console.log("Taxonomy resolveChildren with options and taxonomy node key:");
console.log(node);
```

TypeScript

```
const node = await client.taxonomy.resolveChildren({
  node: { key: "0/1", name: "", path: "", hasChildren: true },
  order: "defined",
  childDepth: 99,
  language: "fr-FR",
});
console.log("Taxonomy resolveChildren with options and taxonomy node:");
console.log(node);
```

## On this page

-   [Properties](#properties)
-   [Example](#example)