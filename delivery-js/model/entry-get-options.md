## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

Entry Get Options is a structure that is used to describe details for requesting an entry

## Properties

Name

Type

Description

id

string

The id of the entry.

language

string

The language variation to return for each entry.

linkDepth

number

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10.

fields

string \[...\]

An array of field ids to restrict the fields returned for an entry.

fieldLinkDepths

{ string: number }

Object containing field paths to resolve linked entries for and the link depth to resolve the field to