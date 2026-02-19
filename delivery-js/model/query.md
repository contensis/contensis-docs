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
-   [Parameters](#parameters)
-   [Returns](#returns)

A Query allows us to provide a nested structure of expressions (as [Operators](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/search/query-operators)) that contain criteria that we can use with the `entries.search()` method in a Delivery API client. The returned object allows us to add additional refinements to the search before the request for content is made, such as specifying the pageIndex, the ordering of results, or which fields to return.

### Call signature

TypeScript

```
new Query(...whereExpressions: Operators[]): Query
```

### Parameters

Name

Type

Description

whereExpressions

`[Operators](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/search/query-operators)[]`

An array of search expressions constructed as Operators

### Returns

An instance of `Query` we can set specific properties and use with `entries.search()`

## Properties

Name

Type

Description

where

[`WhereExpression`](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/search/search-basics)

Read or refine query expressions

pageSize

`number`

The size of each page of search results

pageIndex

`number`

The index of subsequent pages of search results (required if > 0)

orderBy

`string | string[] | [OrderBy](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/search/search-basics)`

Sort search results by one or more content fields

fields

`string [ ... ]`

A list of entry fields that will be retrieved (if the returned entries contain them)

fieldLinkDepths

`{ string: number }`

Object containing field paths to resolve linked entries for and the link depth to resolve the field to

aggregations

`QueryAggregations`

Object defining aggregations of field data to return along with the page of search results

## On this page

-   [Call signature](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)