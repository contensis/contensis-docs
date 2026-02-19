## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 23 July 2025

`NodeGetCanonicalByEntryOptions` is a structure that is used to describe the options for requesting the canonical node assigned to an entry.

## Properties

Name

Type

Description

entryId

`string`

The entry id to find the canonical node for

entry

[`Entry`](/help-and-docs/apis/delivery-js/model/entry)

The entry (containing the id) to find the canonical node for

canonicalOnly

`true`

Must be `true` in order to return the canonical node

depth

`number`

The depth of descendants to include for the node. The default is *0*. Also `canonicalOnly` must be `true` to use `depth`

language

`string`

The optional language for the node. If no value is provided then the project default language is used.

entryFieldLinkDepths

`{ string: number }`

Object containing field paths to resolve linked entries for and the link depth to resolve the field to

entryFields

`string[]`

The optional list of fields that will be retrieved if the node has an entry attached to it.

entryLinkDepth

`number`

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10. The default is *0.*