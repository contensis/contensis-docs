1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Key concepts
5.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 08 September 2025

Requesting [nodes](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/node) that have an attached entry can be achieved by using one of the `GetByEntryId` method overloads.

-   [GetByEntryId(Guid entryId)](#get-by-entry-guid-id)
-   [GetByEntryIdAsync(Guid entryId)](#get-by-entry-guid-id-async)
-   [GetByEntryId(string entryId)](#get-by-entry-string-id)
-   [GetByEntryIdAsync(string entryId)](#get-by-entry-string-id-async)

## Get by entry Guid id

Gets a list of nodes by specifiying an entry `Guid` identifier.

### Syntax

C#

```
public List<Node> GetByEntryId(Guid entryId)
{
}
```

### Parameters

*id*

Type: `Guid`  
The entry identifier to match the nodes by.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get a specific node with assigned entry id
List<Node> nodesWithEntryAssigned = movieDbProject.Nodes.GetByEntryId(entryGuid);
```

## Get by entry Guid id async

Gets a list of nodes asynchronously by specifiying an entry `Guid` identifier.

### Syntax

C#

```
public async Task<List<Node>> GetByEntryIdAsync(Guid entryId)
{
}
```

### Parameters

*id*

Type: `Guid`  
The entry identifier to match the nodes by.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get a specific node with assigned entry id
List<Node> nodesWithEntryAssigned = await movieDbProject.Nodes.GetByEntryIdAsync(entryGuid);
```

## Get by entry string id

Gets a list of nodes by specifiying an entry `string` identifier.

### Syntax

C#

```
public List<Node> GetByEntryId(string entryId)
{
}
```

### Parameters

*id*

Type: `string`  
The entry identifier to match the nodes by.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get a specific node with assigned entry id
List<Node> nodesWithEntryAssigned = movieDbProject.Nodes.GetByEntryId("d2fb1cb7-e0c0-4334-bf86-be0f08163953");
```

## Get by entry string id async

Gets a list of nodes asynchronously by specifiying an entry `string` identifier.

### Syntax

C#

```
public async Task<List<Node>> GetByEntryIdAsync(string entryId)
{
}
```

### Parameters

*id*

Type: `string`  
The entry identifier to match the nodes by.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get a specific node with assigned entry id
List<Node> nodesWithEntryAssigned = await movieDbProject.Nodes.GetByEntryIdAsync("d2fb1cb7-e0c0-4334-bf86-be0f08163953");
```