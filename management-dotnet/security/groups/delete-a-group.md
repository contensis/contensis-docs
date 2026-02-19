1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Security
5.  Groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Deleting a [group](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/group) can be achieved by using one of the Delete method overloads.

-   [Delete()](#delete)
-   [DeleteAsync()](#delete-async)

## Delete

Deletes a group.

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
var groupId = Guid.Parse("c5da1719-cb3f-4f2e-927b-f678293258f3");

// Get the group
Group group = client.Security.Groups.Get(groupId);

// Delete the group
group.Delete();
```

## Delete async

Deletes a group asynchronously.

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
var groupId = Guid.Parse("c5da1719-cb3f-4f2e-927b-f678293258f3");

// Get the group
Group group = await client.Security.Groups.GetAsync(groupId);

// Delete the group
await group.DeleteAsync();
```