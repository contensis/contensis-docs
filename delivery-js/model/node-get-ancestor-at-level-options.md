## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

`NodeGetAncestorAtLevelOptions` is a structure that is used to describe the options for requesting a node ancestor at a specified level.

## Properties

Name

Type

Description

id?

`string`

The node id.

node?

[`Node`](https://www.contensis.com/help-and-docs/apis/delivery-js/model/node)

The node object.

language?

`string`

The optional language for the node. If no value is provided then the project default language is used.

startLevel?

`number`

The start level at which the ancestor lookup starts.

depth?

`number`

The depth of descendants to include for the node. The default is *0*. This reduces calls to the HTTP service and improves performance.

entryFieldLinkDepths?

`{ string: number }`

Object containing field paths to resolve linked entries for and the link depth to resolve the field to

entryFields?

`string[]`

The optional list of fields that will be retrieved if the node has an entry attached to it.

entryLinkDepth?

`number`

The depth at which to resolve the full entry data for a linked entry or asset, with a maximum depth value of 10. The default is *0.*