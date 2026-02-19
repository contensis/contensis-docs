1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

It represents the client API configuration.

## Properties

Name

Type

Format

Description

rootUrl?

string

The root url of the Contensis instance

projectId?

string

The Contensis project id

clientType?

string

The client type value which for most types of projects is 'client\_credentials'

clientDetails?

object

The client details object

clientDetails.clientId

string

The client id value taken from the API key created in Contensis

clientDetails.clientSecret

string

The client id value taken from the API key created in Contensis

language?

string

The default language

versionStatus?

string

'latest', 'published'

The version status of the items retrieved by the API calls. The default value is *latest*

pageIndex?

number

The page index for the items retrieved by the API calls. The default value is *0*

pageSize?

number

The page size of the items retrieved by the API calls. The default value is *25*