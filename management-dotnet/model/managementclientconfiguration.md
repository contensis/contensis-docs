1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 09 December 2024

The `ManagementClientConfiguration` is a container for the options that are required for setting the default settings.

## Syntax

C#

```
// Constructor.
public ManagementClientConfiguration(string rootUrl, string clientId = null, string sharedSecret = null)
{
}
```

### Parameters

*rootUrl*

Type: `string`  
The url to the root of the Management API services.

*clientId*

*sharedSecret*

## Properties

Name

Type

Description

RootUrl

string

The url to the root of the Management API services.

ClientId

string

The client id value obtained from [API key management](https://www.contensis.com/help-and-docs/guides/integrating-with-other-platforms/api-keys/api-key-overview "API Keys").

SharedSecret

string

The shared secret value obtained from [API key management](https://www.contensis.com/help-and-docs/guides/integrating-with-other-platforms/api-keys/api-key-overview "API Keys").

## Example

C#

```
// Set the default settings which will be used when client instances are created without parameters.
using Zengenti.Contensis.Management;

var defaultConfiguration = new ManagementClientConfiguration(
    rootUrl: "http://cms.contensis.com",
    clientId: "651465e0-2fb8-4b0f-aa2f-1ab34cfe0513",
    sharedSecret: "2327d623-d44e-41ef-a837-717a626f4b75-098348eb-b0a6-4023-a64a-805536024dfb-1a558c9c-49dc-4709-9e8b-c203f60fda80"
);

// Set the default settings.
ManagementClient.Configure(defaultConfiguration);

// The client instance will use the default settings.
var client = ManagementClient.Create();
```