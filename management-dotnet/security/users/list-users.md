1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Listing [users](/help-and-docs/apis/management-dotnet/model/user) can be achieved by using one of the `List` method overloads.

-   [List(SecurityListOptions listOptions)](#list-with-page-options)
-   [ListAsync(SecurityListOptions listOptions)](#list-with-page-options-async)
-   [List(SecurityListOptions listOptions, string query)](#list-with-query)
-   [ListAsync(SecurityListOptions listOptions, string query)](#list-with-query-async)

List users specifying page options.

### Syntax

C#

```
public PagedList<User> List(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

*query*

Type: `string`  
The optional user list query, which performs a basic `contains` on the users firstname, surname, username or email.

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

// List the users
PagedList<User> users = client.Security.Users.List(listOptions);
```

List users specifying page options asynchronously.

### Syntax

C#

```
public async Task<PagedList<User>> ListAsync(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

*query*

Type: `string`  
The optional user list query, which performs a basic `contains` on the users firstname, surname, username or email.

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

// List the users
PagedList<User> users = await client.Security.Users.ListAsync(listOptions);
```

List users specifying a query to filter users by.

### Syntax

C#

```
public PagedList<User> List(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

Type: `SecurityListOptions`  
The list options, page size, page index, etc.

*query*

Type: `string`  
The optional user list query, which performs a basic `contains` on the users firstname, surname, username or email.

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

// List the users with a query value of "tyler"
PagedList<User> users = client.Security.Users.List(listOptions, "tyler");
```

List users specifying a query to filter users by asynchronously.

### Syntax

C#

```
public async Task<PagedList<User>> ListAsync(SecurityListOptions listOptions = null, string query = null)
{    
}
```

### Parameters

*listOptions*

Type: `SecurityListOptions`  
The list options, page size, page index, etc.

*query*

Type: `string`  
The optional user list query, which performs a basic `contains` on the users firstname, surname, username or email.

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

// List the users with a query value of "tyler"
PagedList<User> users = await client.Security.Users.ListAsync(listOptions, "tyler");
```