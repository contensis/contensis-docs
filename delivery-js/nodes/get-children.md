## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)

Call the nodes.getChildren() method in our delivery client to get the child nodes of an existing [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) from site view, optionally resolving an attached [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
getChildren(id: string): Promise<Node[]>

getChildren(node: Node): Promise<Node[]>

getChildren(options: NodeGetChildrenOptions): Promise<Node[]>
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

[NodeGetChildrenOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-children-options)

An options object to apply additional refinements

### Returns

A Promise that will resolve an array of [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

### Remarks

Returns an empty array if no nodes exist with the specified entry

Throws any error that is returned by the API for any other unsuccessful request echoing the HTTP status returned from the API

### Example

Get the child nodes of an existing node

TypeScript

```
const children = await client.nodes.getChildren(
  "7a301bf2-96c3-461c-8068-bebe6783ecc5"
);

for (const node of children) {
  console.log(node.path);
}
```

Get the child nodes of an existing node also resolving the entryTitle field of any entry attached to the returned nodes

TypeScript

```
const children = await client.nodes.getChildren({
  id: "7a301bf2-96c3-461c-8068-bebe6783ecc5",
  entryFields: ["entryTitle"],
});

for (const node of children) {
  console.log(`${node.path} ${node.entry?.entryTitle}`);
}
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)