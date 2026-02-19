1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Listing the child [groups](/help-and-docs/apis/management-dotnet/model/group) for a group can be achived by using one of the `Children` method overloads.

-   [Children(SecurityListOptions listOptions)](#list-with-page-options)
-   [ChildrenAsync(SecurityListOptions listOptions)](#list-with-page-options-async)

## List with page options

Lists child groups, specifying page options.

### Syntax

C#

```
public PagedList<Group> Children(SecurityListOptions listOptions = null)
{    
}
```

### Parameters

*listOptions*

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

Group systemAdministrators = client.Security.Groups.Get("System Administrators");

// Setup the list options, setting a page size of 10 and ordering by group name
SecurityListOptions listOptions = new SecurityListOptions
{
    PageOptions = new PageOptions(0, 10),
    Order = "name"
};

// List the child groups
PagedList<Group> groups = systemAdministrators.Children(listOptions);
```

## List with page options async

Lists child groups, specifying page options asynchronously.

### Syntax

C#

```
public Task<PagedList<Group>> ChildrenAsync(SecurityListOptions listOptions = null)
{    
}
```

### Parameters

*listOptions*

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

Group systemAdministrators = await client.Security.Groups.GetAsync("System Administrators");

// Setup the list options, setting a page size of 10 and ordering by group name
SecurityListOptions listOptions = new SecurityListOptions
{
    PageOptions = new PageOptions(0, 10),
    Order = "name"
};

// List the child groups
PagedList<Group> groups = await systemAdministrators.ChildrenAsync(listOptions);
```