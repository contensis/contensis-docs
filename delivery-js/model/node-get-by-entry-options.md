## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

`NodeGetByEntryOptions` is a structure that is used to describe the options for requesting the nodes assigned to an entry.

## Properties

Name

Type

Description

entryId?

`string`

The entry id.

entry?

[`Entry`](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

The entry.

language?

`string`

The optional language for the node. If no value is provided then the project default language is used.

entryFieldLinkDepths?

`{ string: number }`

Object containing field paths to resolve linked entries for and the link depth to resolve the field to

entryFields?

`string[]`

The optional list of fields that will be retrieved if the node has an entry attached to it.

entryLinkDepth?

`number`

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10. The default is *0.*