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

Entry List Options is a structure that is used to describe details for requesting entry listing results

## Properties

Name

Type

Description

contentTypeId

string

The id of the content type.

fieldLinkDepths

{ string: number }

Object containing field paths to resolve linked entries for and the link depth to resolve the field to

fields

string \[...\]

An array of field ids to restrict the fields returned for an entry.

language

string

The language variation to return for each entry.

linkDepth

number

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10.

order

string \[...\]

An array of field ids to order the results by. Descending order is specified using a prefixed '-'.

pageOptions

PageOptions

An object specifying the pageSize and pageIndex.

## Example

## On this page

-   [Properties](#properties)
-   [Example](#example)