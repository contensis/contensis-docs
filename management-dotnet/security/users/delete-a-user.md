1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Deleting a [user](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/user) can be achieved by using one of the Delete method overloads.

-   [Delete()](#delete)
-   [DeleteAsync()](#delete-async)

## Delete

Deletes a user.

### Syntax

C#

```
public void Delete()
{    
}
```

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Mimic a guid value
var userId = Guid.Parse("c5da1719-cb3f-4f2e-927b-f678293258f3");

// Get the user
User user = client.Security.Users.Get(userId);

// Delete the user
user.Delete();
```

## Delete async

Deletes a user asynchronously.

### Syntax

C#

```
public async Task DeleteAsync()
{    
}
```

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Mimic a guid value
var userId = Guid.Parse("c5da1719-cb3f-4f2e-927b-f678293258f3");

// Get the user
User user = await client.Security.Users.GetAsync(userId);

// Delete the user
await user.DeleteAsync();
```