1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Requesting an individual project can be achieved by using one of the *Get* operations.

-   [Get(string projectId)](#get-by-id)
-   [GetAsync(string projectId)](#get-by-id-async)

## Get by id

Gets a project by its identifier.

### Syntax

C#

```
public Project Get(string projectId)
{
}
```

### Parameters

*id*

Type: `string`  
The id of the project.

### Remarks

Returns *null* if a project with an id matching the specified id does not exist.

## Example

This example shows how a project instance can be accessed.

C#

```
using Zengenti.Contensis.Management;

var client = ManagementClient.Create();

// Access the movie DB project
var movieProject = client.Projects.Get("movieDb");
```

## Get by id async

Gets a project by its identifier asynchronously.

### Syntax

C#

```
public async Task<Project> GetAsync(string projectId)
{
}
```

### Parameters

*id*

Type: `string`  
The id of the project.

### Remarks

Returns *null* if a project with an id matching the specified id does not exist.

## Example

This example shows how a project instance can be accessed asynchronously.

C#

```
using Zengenti.Contensis.Management;

var client = ManagementClient.Create();

// Access the movie DB project
var movieProject = await client.Projects.GetAsync("movieDb");
```