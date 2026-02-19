1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 August 2024

Searching [users](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/user) can be achieved by using one of the Search methods.

-   [Search(SecuritySearchOptions securitySearchOptions)](#search-with-search-options)
-   [SearchAsync(SecuritySearchOptions securitySearchOptions)](#search-with-search-options-async)

Search users specifying options.

### Syntax

C#

```
public PagedList<User> Search(SecuritySearchOptions securitySearchOptions)
{    
}
```

### Parameters

*securitySearchOptions*

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;

// Create a client
var client = ManagementClient.Create();

SecuritySearchOptions securitySearchOptions = new SecuritySearchOptions 
{
    PageIndex = 0,
    PageSize = 10,
    OrderBy = new List<string>{"username"},
    Where = new IExpression[]
    {
        new OrExpression(
            new Contains("email", "zengenti"),
            new EqualTo<string>("username", "zengenti")
         )
     }
};

// Search the users
PagedList<User> users = client.Security.Users.Search(securitySearchOptions);
```

Search users asynchronously specifying options.

### Syntax

C#

```
public Task<PagedList<User>> SearchAsync(SecuritySearchOptions securitySearchOptions)
{    
}
```

### Parameters

*securitySearchOptions*

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;

// Create a client
var client = ManagementClient.Create();

SecuritySearchOptions securitySearchOptions = new SecuritySearchOptions 
{
    PageIndex = 0,
    PageSize = 10,
    OrderBy = new List<string>{"username"},
    Where = new IExpression[]
    {
        new OrExpression(
            new Contains("email", "zengenti"),
            new EqualTo<string>("username", "zengenti")
         )
     }
};

// Search the users
PagedList<User> users = await client.Security.Users.SearchAsync(securitySearchOptions);
```