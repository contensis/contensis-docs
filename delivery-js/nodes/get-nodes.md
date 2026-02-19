1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 23 July 2025

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Remarks](#remarks)
-   [Example](#example)
-   [Get nodes by entry](#get-nodes-by-entry)
-   [Call signatures](#call-signatures-1)
-   [Parameters](#parameters-1)
-   [Remarks](#remarks-1)
-   [Examples](#examples)

Call the `nodes.get()` method in our delivery client to return a [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) from site view, optionally resolving an attached [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
get(id: string): Promise<Node>

get(path: string): Promise<Node>

get(options: NodeGetByIdOptions): Promise<Node>

get(options: NodeGetByPathOptions): Promise<Node>
```

### Parameters

Name

Type

Description

id

`string`

The id of the node

path

`string`

The full path to the node

options

`[NodeGetByIdOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-by-id-options)`

An options object to apply additional refinements

options

`[NodeGetByPathOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-by-path-options)`

An options object to apply additional refinements

### Returns

A Promise that will resolve with the [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) or array of [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

### Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

### Example

Get a node by its ID

TypeScript

```
const node = await client.nodes.get("57d77dbc-49da-40ca-aaaf-3b877b69699a");
```

Get a node by a path, resolving all fields in any entry attached to the found node while handling any errors

TypeScript

```
try {
  const node = await client.nodes.get({
    path: "/about/contact",
    entryFields: ["*"],
  });
  if (node) {
    // the node is available
    console.log(node.path);
    if (node.entry) {
      // the node has an entry attached
      console.log(node.entry.entryTitle);
    }
  }
} catch (error) {
  if ("status" in error)
    // format the error message returned from the api
    console.error(
      `[${error.status} ${error.statusText}] ${error.data?.message}`
    );
  // log the raw error
  else console.error(error);
}
```

## Get nodes by entry

Call the `nodes.getByEntry()` method in our delivery client to return an array of [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node), or a single canonical [node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) from site view, optionally resolving the attached [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Call signatures

TypeScript

```
getByEntry(entryId: string): Promise<Node[]>

getByEntry(entry: Entry): Promise<Node[]>

getByEntry(options: NodeGetByEntryOptions): Promise<Node[]>

getByEntry(options: NodeGetCanonicalByEntryOptions): Promise<Node>
```

### Parameters

Name

Type

Description

entryId

`string`

The id of the entry attached to the node(s)

entry

`Entry`

An entry object containing the sys.id of the entry attached to the node(s)

options

`[NodeGetByEntryOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-by-entry-options)`

An options object to apply additional refinements

options

`[NodeGetCanonicalByEntryOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node-get-canonical-by-entry-options)`

An options object to request a single canonical node

### Returns

A Promise that will resolve with an array of [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node), or a single canonical [Node](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node) if `NodeGetCanonicalByEntryOptions` are provided.

### Remarks

Returns an empty array if no nodes exist with the specified entry or a 404 error if `NodeGetCanonicalByEntryOptions` are provided.

### Examples

Get all nodes that have the entry with the supplied entry ID attached

TypeScript

```
const nodes = await client.nodes.getByEntry(
  "ba950397-5e7c-4847-a07f-cf015b9e59cb"
);

if (nodes.length > 0) {
  console.log(nodes[0].path);
} else {
  console.error("no nodes were found");
}
```

Get all nodes that have the supplied entry attached

TypeScript

```
import type { Entry, EntrySys } from "contensis-delivery-api";

const entry: Entry = {
  entryTitle: "An entry",
  sys: {
    id: "ba950397-5e7c-4847-a07f-cf015b9e59cb",
    contentTypeId: "movie",
  } as EntrySys,
};

const nodes = await client.nodes.getByEntry(entry);

for (const node of nodes) {
  console.log(node.path);
}
```

Get the canonical node that has the entry with the supplied entry ID attached and return the node's children to a depth of 1

TypeScript

```
const node = await client.nodes.getByEntry(
  {
    canonicalOnly: true,
    depth: 1,
    entryId: "ba950397-5e7c-4847-a07f-cf015b9e59cb"
  }
);

console.log(node.path);

for (const childNode of node.children) {
  console.log(childNode.path);
}
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Remarks](#remarks)
-   [Example](#example)
-   [Get nodes by entry](#get-nodes-by-entry)
-   [Call signatures](#call-signatures-1)
-   [Parameters](#parameters-1)
-   [Remarks](#remarks-1)
-   [Examples](#examples)