1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Security
5.  Groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Creating and updating [groups](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/group) can be achieved by using one of the `New` method overloads in combination with calling `Save` on the Group class.

-   [New(string groupName, GroupType groupType)](#create-new-group)

Initializes a new group with a group name and type. The group is not created from calling `New`.

### Syntax

C#

```
public Group New(string groupName, GroupType groupType)
{    
}
```

### Parameters

*groupName*

Type: `string`  
The group name.

*groupType*

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Initialize the group
Group group = client.Security.Groups.New("Fight Club Members", GroupType.Contensis);

// Create the group
group.Save();

// Create the group asynchronously
await group.SaveAsync();
```

Updates an existing group.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get an existing group
Group group = client.Security.Groups.Get("Fight Club Members");

// Update group details
group.Description = "Members of Fight Club";

// Update the group
group.Save();

// Update the group asynchronously
await group.SaveAsync();
```