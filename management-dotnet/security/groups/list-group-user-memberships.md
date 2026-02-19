1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Groups

[Log in to add to favourites](/account/login)

Page last updated 12 July 2022

Listing the [users](/help-and-docs/apis/management-dotnet/model/user) that are members of [groups](/help-and-docs/apis/management-dotnet/model/group) can be achieved by using one of the `Users` method overloads.

-   [Users(SecurityListOptions listOptions)](#list-with-page-options)
-   [UsersAsync(SecurityListOptions listOptions)](#list-with-page-options-async)

List users that are members of the group.

### Syntax

C#

```
public PagedList<User> List(SecurityListOptions listOptions = null)
{    
}
```

### Parameters

*listOptions*

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

// Get the group
Group group = client.Security.Groups.Get("System Administrators");

// List the users
PagedList<User> members = group.Users(listOptions);
```

List users that are members of the group asynchronously.

### Syntax

C#

```
public Task<PagedList<User>> List(SecurityListOptions listOptions = null)
{    
}
```

### Parameters

*listOptions*

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

// Get the group
Group group = await client.Security.Groups.Get("System Administrators");

// List the users
PagedList<User> members = await group.UsersAsync(listOptions);
```