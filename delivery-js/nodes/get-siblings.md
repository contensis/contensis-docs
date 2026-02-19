## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Nodes

[Log in to add to favourites](/account/login)

Page last updated 13 November 2024

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters-8)
-   [Returns](#returns)
-   [Remarks](#remarks-3)
-   [Example](#example)

Call the nodes.getSiblings() method in our delivery client to get the sibling nodes of an existing [node](/help-and-docs/apis/delivery-js/model/node) from site view, optionally resolving an attached [entry](/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
getSiblings(id: string): Promise<Node[]>

getSiblings(node: Node): Promise<Node[]>

getSiblings(options: NodeGetSiblingOptions): Promise<Node[]>
```

### Parameters

Name

Type

Description

id

string

The id of the node

node

[Node](/help-and-docs/apis/delivery-js/model/node)

A node object

options

[NodeGetSiblingOptions](/help-and-docs/apis/delivery-js/model/node-get-siblings-options)

An options object to apply additional refinements

### Returns

A Promise that will resolve an array of [Node](/help-and-docs/apis/delivery-js/model/node)

### Remarks

Returns an empty array if no sibling nodes are returned

Throws any error that is returned by the API for any other unsuccessful request echoing the HTTP status returned from the API

### Example

Get the sibling nodes of an existing node

TypeScript

```
const node = await client.nodes.getSiblings(
  "7a301bf2-96c3-461c-8068-bebe6783ecc5"
);

for (const node of nodes) {
  console.log(node.path);
}
```

Get the sibling nodes of an existing node also resolving the entryTitle field of any entry attached to the returned nodes

TypeScript

```
const nodes = await client.nodes.getSiblings({
  id: "7a301bf2-96c3-461c-8068-bebe6783ecc5",
  entryFields: ["entryTitle"],
});

for (const node of nodes) {
  console.log(
    node.path,
    node.childCount ? `+${node.childCount}` : "",
    node.entry?.entryTitle || ""
  );
}
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters-8)
-   [Returns](#returns)
-   [Remarks](#remarks-3)
-   [Example](#example)