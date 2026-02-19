1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Getting a list of projects can be achieved by using one of the `List` method overloads.

-   [List()](#list)
-   [ListAsync()](#list-async)

## List

Lists all projects for a Contensis instance.

### Syntax

C#

```
public List<Project> List()
{
}
```

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// List projects
var projects = client.Projects.List();
```

## List async

Lists all projects for a Contensis instance asynchronously.

### Syntax

C#

```
public async Task<List<Project> ListAsync()
{
}
```

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// List projects
var projects = await client.Projects.ListAsync();
```