1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 19 May 2022

## Deprecation warning

Taxonomy in entries is deprecated and may be removed from future releases of Contensis. We *strongly* recommend using content types and entries to categorise content.

Taxonomy nodes can be retrieved using the following methods, either by key or by path. The localization can be included as a parameter to determine the language the nodes should be returned as. The order by default is set to 'alphabetical', but an order of 'defined' (which is the order set in the UI) can also be used.

The childDepth parameter is used to reduce the number of service calls if child and descendant nodes are being iterated, which will potentially increase performance.

-   [getNodeByKey(key: string | TaxonomyGetNodeByKeyOptions): Promise <TaxonomyNode>](#getnodebykey)
-   [getNodeByPath(path: string | TaxonomyGetNodeByPathOptions): Promise <TaxonomyNode>](#getnodebypath)
-   [resolveChildren(node: string | TaxonomyNode | TaxonomyResolveChildrenOptions): Promise <TaxonomyNode>](#resolvechildren)

## getNodeByKey

A function that uses a taxonomy node key to retrieve taxonomy nodes. It returns a Promise that will resolve with a [TaxonomyNode](https://www.contensis.com/help-and-docs/apis/delivery-js/model/taxonomy-node) instance.

### Syntax

### Parameters

*key*

Type: `string`  
The key for the taxonomy, which is a forward-slash delimited set of integer values, e.g. 0/2/734

or

*key*

### Example

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

## getNodeByPath

A function that uses a taxonomy node path to retrieve taxonomy nodes. It returns a Promise that will resolve with a [TaxonomyNode](https://www.contensis.com/help-and-docs/apis/delivery-js/model/taxonomy-node) instance.

### Syntax

### Parameters

*path*

Type: `string`  
The path for the taxonomy, which is a forward-slash delimited set of string values, e.g. "Root/Movies/Genres/Comedy"

or

*path*

### Example

TypeScript

```
const node = await client.taxonomy.getNodeByPath("Root/StructuredContent");
console.log("Taxonomy getNodeByPath:");
console.log(node);
```

TypeScript

```
const node = await client.taxonomy.getNodeByPath({
  path: "Root/StructuredContent",
  order: "defined",
  childDepth: 10,
  language: "fr-FR",
});
console.log("Taxonomy getNodeByPath with options:");
console.log(node);
```

## resolveChildren

A function that uses a taxonomy node key or a taxonomy node instance to resolve taxonomy nodes. It returns a Promise that will resolve with a [TaxonomyNode](https://www.contensis.com/help-and-docs/apis/delivery-js/model/taxonomy-node) instance.

### Syntax

### Parameters

*node*

Type: `string`  
The key for the taxonomy, which is a forward-slash delimited set of integer values, e.g. 0/2/734

or

*node*

or

*node*

### Example

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