## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 29 May 2025

## On this page

-   [Call signature](#call-signatures)
-   [Parameters](#parameters-1)
-   [Returns](#returns-1)

A ZenqlQuery allows us to provide a ZenQL statement to the `entries.search()` method in a Delivery API client. The returned object allows us to add additional refinements to the search before the request for content is made, such as specifying a pageIndex or fields to return.

### Call signature

TypeScript

```
new ZenqlQuery(zenql: string): ZenqlQuery
```

### Parameters

Name

Type

Description

zenql

`string`

A ZenQL statement containing the search criteria for returning entries

### Returns

An instance of `ZenqlQuery` we can set specific properties and use with `entries.search()`

## Properties

Name

Type

Description

zenql

`string`

A ZenQL statement containing the search criteria for returning entries

pageIndex

`number`

The index of subsequent pages of search results (required if > 0)

pageSize

`number`

The size of each page of search results

fieldLinkDepths

`{ string: number }`

Object containing field paths to resolve linked entries for and the link depth to resolve the field to

fields

`string [ ... ]`

A list of entry fields that will be retrieved (if the returned entries contain them)

aggregations

[`QueryAggregations`](https://www.contensis.com/help-and-docs/apis/delivery-js/model/query-aggregations)

Object defining aggregations of field data to return along with the page of search results

## On this page

-   [Call signature](#call-signatures)
-   [Parameters](#parameters-1)
-   [Returns](#returns-1)