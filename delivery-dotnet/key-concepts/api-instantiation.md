1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 10 December 2024

## Installation

The Contensis .NET Delivery API targets .NET Standard 2.0, which means it can be used in .NET Framework 4.6.2 projects and above for Windows only, and .NET Core 2.0 projects and above for Windows, Linux and MacOS.

The Nuget package can be added to a project using the built-in Visual studio Nuget management screens or by using one of the following methods.

-   Open the Package Manager Console window within Visual Studio and run the following command:

Bash

```
PM> Install-Package Zengenti.Contensis.Delivery
```

-   Open a command window and run the following .NET CLI command:

Bash

```
dotnet add package Zengenti.Contensis.Delivery
```

NOTE: You may have to target a previous major version of the API to match your version of Contensis.

## Client creation

All operations for the API hang off the *ContensisClient* type, which is created using the static method `ContensisClient.Create()`. The `Create()` method allows parts of the [default configuration](#default-configuration) to be partially or completely overridden for that instance.

### Standard creation

This is how the majority of clients are created within Contensis razor views.

C#

```
var client = ContensisClient.Create();
```

### Connecting to a different project

Connecting to a different project is useful if there is a shared resources project. The projectID can be found in the project overview screen in the management console.

C#

```
var sharedResourcesClient = ContensisClient.Create("PUT_PROJECT_ID_HERE");
```

### Connecting from a non-Contensis website

Creating a client from outside a Contensis website.

C#

```
var client = ContensisClient.Create("PUT_PROJECT_ID_HERE", "http://cms.contensis.com", "PUT_CLIENT_ID_HERE", "PUT_SHARED_SECRET_HERE", versionStatus = VersionStatus.Latest);
```

## Default configuration

The default configuration can be only set once. For a Contensis published website this is automatically invoked on application start-up to reflect the context of the publishing server, ensuring that the correct service root url, project API id and version status (Published or Latest) are set.

The default configuration becomes effective for all ContensisClient instantiations, negating the need to provide configuration values each and every time the API is used.

## Non-Contensis published websites

This is a useful feature for websites that are created using a .NET based framework such as NancyFx or Asp.net MVC.

The client ID and shared secret are obtained from [API key management](https://www.contensis.com/help-and-docs/guides/integrating-with-other-platforms/api-keys/api-key-overview "API Keys"). They can then be used to call the security service to obtain a claims-based bearer token, and to validate that the user can access resources from the service.

### API initialisation example

This example demonstrates how the default configuration can be set using the [ContensisClientConfiguration](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/contensisclientconfiguration) type.

C#

```
using Zengenti.Contensis.Delivery;

var defaultConfiguration = new ContensisClientConfiguration(
    rootUrl: "http://cms.contensis.com",
    projectApiId: "myProject",
    defaultVersionStatus: VersionStatus.Latest, // default: Published
    clientId: "651465e0-2fb8-4b0f-aa2f-1ab34cfe0513",
    sharedSecret: "2327d623d44e41efa837717a626f4b75098348ebb0a64023a64a805536024dfb1a558c9c49dc47099e8bc203f60fda80"
);

ContensisClient.Configure(defaultConfiguration);
```