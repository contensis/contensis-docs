1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Delivery API](/help-and-docs/apis/delivery-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 09 December 2024

The ContensisClientConfiguration is a container for the options that are required for setting the defaults settings.

## Syntax

C#

```
// Constructor
public ContensisClientConfiguration(string rootUrl, string projectId, VersionStatus defaultVersionStatus = VersionStatus.Published,
    string clientId = null, string sharedSecret = null)
{
}
```

## Properties

Name

Type

Description

RootUrl

string

The url to the root of the Delivery API services

ProjectId

string

The project identifer, e.g. "movieDb". Found in the project overview screen of the management console

DefaultVersionStatus

VersionStatus

The default version to pass for all [Entry](/help-and-docs/apis/delivery-dotnet/model/entry) requests

ClientId

string

The client id value obtained from [API key management](/help-and-docs/guides/integrating-with-other-platforms/api-keys/api-key-overview "API Keys")

SharedSecret

string

The shared secret value obtained from [API key management](/help-and-docs/guides/integrating-with-other-platforms/api-keys/api-key-overview "API Keys")