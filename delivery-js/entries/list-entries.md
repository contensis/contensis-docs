## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Entries

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Example](#example---using-content-type-id)

Call the entries.search() method in our delivery client to get a paged list of entries for a given search criteria

### Call signatures

TypeScript

```
search(query: Query, linkDepth?: number): Promise<PagedList<Entry>>

search(zenql: string, linkDepth?: number): Promise<PagedList<Entry>>

search(zenqlQuery: ZenqlQuery, linkDepth?: number): Promise<PagedList<Entry>>
```

### Parameters

Name

Type

Description

query

[Query](https://www.contensis.com/help-and-docs/apis/delivery-js/model/query)

A query object containing the search criteria for returning entries

zenql

string

A ZenQL statement containing the search criteria for returning entries

zenqlQuery

[ZenqlQuery](https://www.contensis.com/help-and-docs/apis/delivery-js/model/zenqlquery)

A zenql query object containing the search criteria for returning entries

linkDepth

number

Resolve all fields containing content links in returned entries to this depth

### Returns

A Promise that will resolve with a [Paged List](https://www.contensis.com/help-and-docs/apis/delivery-js/model/paged-list) of [Entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Example

Get a list of published entries of a given content type API ID using search

JavaScript

```
// Using TypeScript, or ES Module await syntax
import { Query, Op } from "contensis-delivery-api";

const query = new Query(
  Op.equalTo("sys.contentTypeId", "<content-type-id>"),
  Op.equalTo("sys.versionStatus", "published")
);

const entryList = await client.entries.search(query);

for (const entry of entryList.items) {
  console.log(entry.entryTitle);
}
```

Get a list of published entries of a given content type API ID using search

JavaScript

```
// Using Common JS promise callback syntax
const { Query, Op } = require("contensis-delivery-api");

const query = new Query(
  Op.equalTo("sys.contentTypeId", "<content-type-id>"),
  Op.equalTo("sys.versionStatus", "published")
);

client.entries
  .search(query)
  .then(function (entryList) {
    entryList.items.forEach(item => (
        console.log(item.entryTitle)
    ))
  });
```

Get a list of published entries of a given content type API ID using a ZenQL statement

TypeScript

```
const entryList = await client.entries.search(
  "sys.contentTypeId=<content-type-id> and sys.versionStatus=published"
);

for (const entry of entryList.items) {
  console.log(entry.entryTitle);
}
```

Get the third page of published entries of a given content type API ID using ZenQL

TypeScript

```
import { ZenqlQuery } from "contensis-delivery-api";

const query = new ZenqlQuery("sys.contentTypeId=<content-type-id> and sys.versionStatus=published");
query.pageIndex = 2;

const entryList = await client.entries.search(query);

for (const entry of entryList.items) {
  console.log(entry.entryTitle);
}
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Example](#example---using-content-type-id)