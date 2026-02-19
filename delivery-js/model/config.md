## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

A Config is required provide the necessary details to the [Client.create()](https://www.contensis.com/help-and-docs/apis/delivery-js/model/client) method that connects to a Contensis project and allows for further refinements that are applied to each request made from the client instance that is returned

## Properties

Name

Type

Description

rootUrl

string

The api url of the Contensis instance

accessToken

string

The [environment access token](https://www.contensis.com/help-and-docs/guides/managing-your-environment/environment-access-token) to authenticate requests

projectId

string

The project API id to use with the client

language

string

The [language](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization) to request localized content for

versionStatus

"latest" | "published"

The content version to retrieve

pageSize

number

Set the number of results to return per page when requesting a [PagedList](https://www.contensis.com/help-and-docs/apis/delivery-js/model/paged-list)

clientType

ClientGrantType

Authorise client requests using a specific type of credentials

clientDetails

ClientGrants

Authorise client requests using a specific set of credentials

defaultHeaders

{ \[key\]: string}

Any default headers to include with client requests

responseHandler

ResponseHandler

Add a callback function used when a response returns a specific or any HTTP status code

fetchFn

(input: RequestInfo, init?: RequestInit): Promise<Response>

Override the fetch API used when making HTTP requests