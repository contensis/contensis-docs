The Management API has been designed to enable you to create and update content within Contensis as quickly and easily as possible. The API's main purpose is to allow content to be imported into Contensis in a process outside of a website as either a one-off migration or as a scheduled job, although it can be used within a website context if required.

The core Management API is a HTTP RESTful service, exposing content as JSON data and resource files (assets) as text or binary files. The .NET Management Client API is a wrapper to the [HTTP services](https://developer.zengenti.com/contensis/api/management/http/), which simplifies security and data consumption.

This documentation is mainly example-driven with API references to the types.

The .NET Management API is included with Contensis websites, however it can also be used in any .NET Core and .NET Framework project, and is [available as a NuGet package here](https://www.nuget.org/packages/Zengenti.Contensis.Management/).