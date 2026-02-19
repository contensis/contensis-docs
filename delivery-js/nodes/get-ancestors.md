1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters-8)
-   [Returns](#returns)
-   [Remarks](#remarks-3)
-   [Examples](#example)
-   [Get node ancestor at level](#get-node-ancestor-at-level)
-   [Get node parent](#get-node-parent)

Call the nodes.getAncestors() method in our delivery client to get the ancestor nodes of an existing [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) from site view, optionally resolving an attached [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
getAncestors(id: string): Promise<Node[]>

getAncestors(node: Node): Promise<Node[]>

getAncestors(options: NodeGetAncestorsOptions): Promise<Node[]>
```

### Parameters

Name

Type

Description

id

string

The id of the node

node

[Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

A node object

options

[NodeGetAncestorsOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-ancestors-options)

An options object to apply additional refinements

### Returns

A Promise that will resolve an array of [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

### Remarks

If a start level is specified that is equal to or greater than the level of the start node then an empty array will be returned

Throws any error that is returned by the API for any other unsuccessful request echoing the HTTP status returned from the API

### Examples

Get all ancestor nodes of an existing node

TypeScript

```
const nodes = await client.nodes.getAncestors(
  "7a301bf2-96c3-461c-8068-bebe6783ecc5"
);

for (const node of nodes) {
  console.log(node.path);
}
```

Get all ancestor nodes of an existing node starting at level 2 also resolving the entryTitle field of any entry attached to the returned nodes

TypeScript

```
const nodes = await client.nodes.getAncestors({
  id: "7a301bf2-96c3-461c-8068-bebe6783ecc5",
  startLevel: 2,
  entryFields: ["entryTitle"],
});

for (const node of nodes) {
  console.log(`${node.path} ${node.entry?.entryTitle || ""}`);
}
```

## Get node ancestor at level

Call the nodes.getAncestorAtLevel() method in our delivery client to get the ancestor node of an existing [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) at a specific level from site view, optionally resolving an attached [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
getAncestorAtLevel(options: NodeGetAncestorAtLevelOptions): Promise<Node>
```

### Parameters

Name

Type

Description

options

[NodeGetAncestorAtLevelOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-ancestor-at-level-options)

An options object to supply required refinements

### Returns

A Promise that will resolve with a [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

### Remarks

If a level is specified that is equal to or greater than the level of the start node then *null* will be returned

Throws any error that is returned by the API for any other unsuccessful request echoing the HTTP status returned from the API

### Example

Get the ancestor nodes of an existing node at level 2 also resolving the entryTitle field of any entry attached to the returned node

TypeScript

```
const node = await client.nodes.getAncestorAtLevel({
  id: "7a301bf2-96c3-461c-8068-bebe6783ecc5",
  startLevel: 2,
  entryFields: ["entryTitle"],
});
```

## Get node parent

Call the nodes.getParent() method in our delivery client to get the immediate ancestor node of an existing [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) from site view, optionally resolving an attached [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
getParent(id: string): Promise<Node>

getParent(node: Node): Promise<Node>

getParent(options: NodeGetParentOptions): Promise<Node>
```

### Parameters

Name

Type

Description

id

string

The id of the node

node

[Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

A node object

options

[NodeGetParentOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-parent-options)

An options object to apply additional refinements

### Returns

A Promise that will resolve with a [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

### Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

### Examples

Get the parent node of an existing child node by the child node's ID

TypeScript

```
const node = await client.nodes.getParent(
  "7a301bf2-96c3-461c-8068-bebe6783ecc5"
);

console.log(node.path);
```

Get the parent node of an existing child node by the child node's ID supplying specific options

TypeScript

```
const node = await client.nodes.getParent({
  id: "7a301bf2-96c3-461c-8068-bebe6783ecc5",
  language: "en-GB",
  entryFields: ["entryTitle"],
});

console.log(`${node.path} ${node.entry?.entryTitle || ""}`);
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters-8)
-   [Returns](#returns)
-   [Remarks](#remarks-3)
-   [Examples](#example)
-   [Get node ancestor at level](#get-node-ancestor-at-level)
-   [Get node parent](#get-node-parent)