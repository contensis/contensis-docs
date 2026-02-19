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

A paged list is a structure that is used to describe paging details for listing and search results.

## Properties

Name

Type

Format

Description

pageIndex

number

int

The index of the result set to return.

pageSize

number

int

The size of the result set to return. The default is 25.

totalCount

number

int

The total number of results available.

pageCount

number

int

The calculated page count based on the totalCount and pageSize.

items

object \[…\]

A container for the items being returned.

## Example

The paged list properties provide the information required to implement paging

TypeScript

```
const entryList = await client.entries.search(query);

// Items
for (const item of entryList.items)
  console.log(item.entryTitle);

// Page details
console.log(entryList.pageIndex);
console.log(entryList.pageSize);
console.log(entryList.totalCount);
console.log(entryList.pageCount);
```

## On this page

-   [Properties](#properties)
-   [Example](#example)