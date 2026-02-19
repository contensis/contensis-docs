1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Listing [groups](/help-and-docs/apis/management-dotnet/model/group) can be achieved by using one of the `List` method overloads.

-   [List(SecurityListOptions listOptions)](#list-with-page-options)
-   [ListAsync(SecurityListOptions listOptions)](#list-with-page-options-async)
-   [List(SecurityListOptions listOptions, string query)](#list-with-query)
-   [ListAsync(SecurityListOptions listOptions, string query)](#list-with-query-async)

List groups specifying page options.

### Syntax

C#

```
public PagedList<Group> List(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

*query*

Type: `string`  
The optional group list query, which performs a basic `contains` on the group name.

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;

// Create a client
var client = ManagementClient.Create();

SecurityListOptions listOptions = new SecurityListOptions 
{
    PageOptions = new PageOptions(0, 10)
};

// List the groups
PagedList<Group> groups = client.Security.Groups.List(listOptions);
```

List groups specifying page options asynchronously.

### Syntax

C#

```
public async Task<PagedList<Group>> ListAsync(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

*query*

Type: `string`  
The optional group list query, which performs a basic `contains` on the group name.

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;

// Create a client
var client = ManagementClient.Create();

SecurityListOptions listOptions = new SecurityListOptions 
{
    PageOptions = new PageOptions(0, 10)
};

// List the groups
PagedList<Group> groups = await client.Security.Groups.ListAsync(listOptions);
```

List groups specifying a query to filter groups by.

### Syntax

C#

```
public PagedList<Group> List(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

Type: `SecurityListOptions`  
The list options, page size, page index, etc.

*query*

Type: `string`  
The optional group list query, which performs a basic `contains` on the group name.

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;

// Create a client
var client = ManagementClient.Create();

SecurityListOptions listOptions = new SecurityListOptions 
{
    PageOptions = new PageOptions(0, 10)
};

// List the groups with a query value of "fight club"
PagedList<Group> groups = client.Security.Groups.List(listOptions, "fight club");
```

List groups specifying a query to filter groups by asynchronously.

### Syntax

C#

```
public async Task<PagedList<Group>> ListAsync(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

Type: `SecurityListOptions`  
The list options, page size, page index, etc.

*query*

Type: `string`  
The optional group list query, which performs a basic `contains` on the group name.

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;

// Create a client
var client = ManagementClient.Create();

SecurityListOptions listOptions = new SecurityListOptions 
{
    PageOptions = new PageOptions(0, 10)
};

// List the groups with a query value of "fight club"
PagedList<Group> groups = await client.Security.Groups.ListAsync(listOptions, "fight club");
```