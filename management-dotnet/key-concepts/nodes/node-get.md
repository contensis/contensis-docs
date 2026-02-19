1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Key concepts
5.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 01 April 2022

Requesting an individual [node](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/node) can be achieved by using one of the following methods.

-   [Get(Guid id)](#get-by-guid-id)
-   [Get(string id)](#get-by-string-id)
-   [GetAsync(Guid id)](#get-by-guid-id-async)
-   [GetAsync(string id)](#get-by-string-id-async)
-   [GetRoot()](#get-root)
-   [GetRootAsync()](#get-root-async)

## Get by Guid id

Gets a node by its `Guid` identifier.

### Syntax

C#

```
public Node Get(Guid id)
{
}
```

### Parameters

*id*

Type: `Guid`  
The id of the node.

### Remarks

Returns *null* if no node matches the specified id.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Mimic a guid id value
var nodeGuid = Guid.Parse("2c95e478-289d-4d28-8159-02a3f8de5fb4");

// Get a specific node with matching id
Node moviesNode = movieDbProject.Nodes.Get(nodeGuid);
```

## Get by string id

Gets a node by its `string` identifier.

### Syntax

C#

```
public Node Get(string id)
{
}
```

### Parameters

*id*

Type: `string`  
The id of the node.

### Remarks

Returns *null* if no node matches the specified id.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get a specific node with matching id
Node moviesNode = movieDbProject.Nodes.Get("2c95e478-289d-4d28-8159-02a3f8de5fb4");
```

## Get by Guid id async

Gets a node by its `Guid` identifier asynchronously.

### Syntax

C#

```
public async Task<Node> GetAsync(Guid id)
{
}
```

### Parameters

*id*

Type: `Guid`  
The id of the node.

### Remarks

Returns *null* if no node matches the specified id.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Mimic a guid id value
var nodeGuid = Guid.Parse("2c95e478-289d-4d28-8159-02a3f8de5fb4");

// Get a specific node with matching id
Node moviesNode = await movieDbProject.Nodes.GetAsync(nodeGuid);
```

## Get by string id async

Gets a node by its `string` identifier asynchronously.

### Syntax

C#

```
public async Task<Node> GetAsync(string id)
{
}
```

### Parameters

*id*

Type: `string`  
The id of the node.

### Remarks

Returns *null* if no node matches the specified id.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get a specific node with matching id
Node moviesNode = await movieDbProject.Nodes.GetAsync("2c95e478-289d-4d28-8159-02a3f8de5fb4");
```

## Get root

Gets the root node for the project.

### Syntax

C#

```
public Node GetRoot()
{
}
```

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get the root node for the prohect
Node rootNode = movieDbProject.Nodes.GetRoot();
```

## Get root async

Gets the root node for the project asynchronously.

### Syntax

C#

```
public async Task<Node> GetRoot()
{
}
```

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Retrieve the relevant project
var movieDbProject = client.Projects.Get("moviedb");

// Get the root node for the project
Node rootNode = await movieDbProject.Nodes.GetRootAsync();
```