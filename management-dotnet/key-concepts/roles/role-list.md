1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Key concepts
5.  Roles

[Log in to add to favourites](/account/login)

Page last updated 21 April 2022

Requesting a list of role can be achieved by using one of the *List* operations.

-   [List(PageOptions pageOptions = null)](#list)
-   [ListAsync(PageOptions pageOptions = null)](#listasync)

## List

Lists all roles assigned to a project.

### Syntax

C#

```
public PagedList<Role> List(PagingOptions pagingOptions = null)
{
}
```

### Parameters

*pageOptions*

Type: `PageOptions<Role>`  
The options for paging the results.

### Return value

## Remarks

The API Key user must be part of the `Roles Administrators` group to be able to list roles.

## Example

This example shows how roles can be listed for a project.

C#

```
using Zengenti.Contensis.Management;

var client = ManagementClient.Create();

// Access the movie DB project
var project = client.Projects.Get("movieDb");

// List the roles with the default paging options
var roles = project.Security.Roles.List();
```

## ListAsync

Lists all roles assigned to a project asynchronously.

### Syntax

C#

```
public async Task<PagedList<Role>> ListAsync(PagingOptions pagingOptions = null)
{
}
```

### Parameters

*pageOptions*

Type: `PageOptions<Role>`  
The options for paging the results.

### Return value

## Example

This example shows how roles can be listed for a project.

C#

```
using Zengenti.Contensis.Management;

var client = ManagementClient.Create();

// Access the movie DB project
var project = await client.Projects.GetAsync("movieDb");

// List the roles with specific paging options
var roles = await project.Security.Roles.ListAsync(new PageOptions(pageIndex: 0, pageSize: 10));
```