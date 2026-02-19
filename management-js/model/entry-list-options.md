1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

A EntryListOptions is a structure that is used to describe details for requesting entries.

Name

Type

Format

Description

contentTypeId

string

The content type identifier.

versionStatus

string

The version status, either *published* or *latest*. The default is *latest*.

pageOptions

object

[PageOptions](/help-and-docs/apis/management-js/model/page-options)

The page options.

order

string\[\]

A array of field Ids to order the results by. Prefix field Id with - for descending order.

language

string

[LanguageCode](/help-and-docs/apis/management-js/key-concepts/localization)

The variation language code.