1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

A EntryGetOptions is a structure that is used to describe details for requesting an entry.

## Properties

Name

Type

Format

Description

id

string

The content type identifier

versionStatus

string

The version status, either *published* or *latest*. The default is *latest*

version

number

{Major}.{Minor}

The version number of the resource

language

string

[LanguageCode](/help-and-docs/apis/management-js/key-concepts/localization)

The variation language code

## Remarks

If a specific *version* value has been provided then the *versionStatus* value will be ignored.