## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 13 November 2024

A Delivery API Client contains all of the operations we can perform with our content. A [Config](/help-and-docs/apis/delivery-js/model/config) is required to provide the necessary details to the create() method that connects it to a Contensis project and allows for further refinements that are applied to each request made from the client instance that is returned.

TypeScript

```
Client.create(config: Config): Client

Client.configure(config: Config): void
```

Use Client.create() to return a Delivery API Client instance that contains all the methods we can call to fetch content

### Parameters

Name

Type

Description

config

[Config](/help-and-docs/apis/delivery-js/model/config)

An object that provide the necessary details connect to a Contensis project and other refinements

## Static Properties

Name

Type

Description

create

Function

Create a new Delivery API client

configure

Function

Update a Delivery API client configuration

## Properties

Name

Type

Description

contentTypes

ContentTypeOperations

Content types operations

entries

EntryOperations

Entries operations

nodes

NodeOperations

Nodes operations

project

ProjectOperations

Project operations

taxonomy

TaxonomyOperations

Taxonomy operations

clientConfig

[Config](/help-and-docs/apis/delivery-js/model/config)

The config the client was created with

bearerToken

string

The bearer token used for API authentication

bearerTokenExpiryDate

Date

When the API authentication bearer token will expire

refreshToken

string

The refresh token used to reauthenticate an expired session

refreshTokenExpiryDate

Date

When the API refresh token will expire

isBearerTokenExpired

(): boolean

Has the API bearer token expired

isRefreshTokenExpired

(): boolean

Has the API refresh token expired

ensureIsAuthorized

(): Promise<string>

Ensure the client is authorised