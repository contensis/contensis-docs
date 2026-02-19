1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](/account/login)

Page last updated 22 July 2022

Checking a [users](/help-and-docs/apis/management-dotnet/model/user) group memberships can be achieved by using one of the `IsMemberOf` method overloads on the user object.

-   [IsMemberOf(string)](#by-group-name)
-   [IsMemberOf(params string\[\])](#by-group-names)
-   [IsMemberOfAsync(string)](#by-group-name-async)
-   [IsMemberOfAsync(params string\[\])](#by-group-names-async)
-   [IsMemberOf(guid)](#by-group-id)
-   [IsMemberOf(params guid\[\])](#by-group-ids)
-   [IsMemberOfAsync(guid)](#by-group-id-async)
-   [IsMemberOfAsync(params guid\[\])](#by-group-ids-async)
-   [IsMemberOf(string)](#by-group-id-string)
-   [IsMemberOf(params string\[\])](#by-group-id-strings)
-   [IsMemberOfAsync(string)](#by-group-id-string-async)
-   [IsMemberOfAsync(params string\[\])](#by-group-id-strings-async)

## By group name

Checks the user is a member of the specified group.

### Syntax

C#

```
public bool IsMemberOf(string groupName)
{    
}
```

### Parameters

*groupName*

Type: `string`  
The group name to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Check if the user is a member of the System Administrators group
bool isSystemAdmin = user.IsMemberOf("System Administrators");
```

## By group names

Checks the user is a member of at least one of the specified groups.

### Syntax

C#

```
public bool IsMemberOf(params string[] groupNames)
{    
}
```

### Parameters

*groupNames*

Type: `string[]`  
The group names to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Check if the user is a member of the System Administrators or Developers groups
bool isSystemAdmin = user.IsMemberOf("System Administrators", "Developers");
```

## By group name async

Checks the user is a member of the specified group asynchronously.

### Syntax

C#

```
public async Task<bool> IsMemberOfAsync(string groupName)
{    
}
```

### Parameters

*groupName*

Type: `string`  
The group name to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Contensis.Management.Users;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

// Check if the user is a member of the System Administrators group
bool isSystemAdmin = await user.IsMemberOfAsync("System Administrators");
```

## By group names async

Checks the user is a member of a least one of the specified groups asynchronously.

### Syntax

C#

```
public async Task<bool> IsMemberOfAsync(params string[] groupNames)
{    
}
```

### Parameters

*groupNames*

Type: `string[]`  
The group name to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

// Check if the user is a member of the System Administrators or Developers groups
bool isSystemAdmin = await user.IsMemberOfAsync("System Administrators", "Developers");
```

## By group id

Checks the user's group membership by the group identifier.

### Syntax

C#

```
public bool IsMemberOf(Guid groupId)
{    
}
```

### Parameters

*groupId*

Type: `guid`  
The group identifier to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

//Mimic a group guid
Guid groupId = Guid.Parse("94b53068-4501-4ea2-abbd-ba51fed5008e");

// Check if the user is a member of the System Administrators group
bool isSystemAdmin = user.IsMemberOf(groupId);
```

## By group ids

Checks the user's group membership by a list of group identifiers.

### Syntax

C#

```
public bool IsMemberOf(params Guid[] groupIds)
{    
}
```

### Parameters

*groupIds*

Type: `guid[]`  
The group identifiers to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

//Mimic group guids
Guid[] groupIds = {
    Guid.Parse("94b53068-4501-4ea2-abbd-ba51fed5008e"),
    Guid.Parse("ec432ee4-3b15-481b-8509-faceb91e030f")
};

// Check if the user is a member of any of the array of groups
bool isSystemAdmin = user.IsMemberOf(groupIds);
```

## By group id async

Checks the user's group membership by the group identifier asynchronously.

### Syntax

C#

```
public async Task<bool> IsMemberOfAsync(Guid groupId)
{    
}
```

### Parameters

*groupId*

Type: `guid`  
The group identifier to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

//Mimic a group guid
Guid groupId = Guid.Parse("94b53068-4501-4ea2-abbd-ba51fed5008e");

// Check if the user is a member of the System Administrators group
bool isSystemAdmin = await user.IsMemberOfAsync(groupId);
```

## By group ids async

Checks the user's group membership by a list of group identifiers.

### Syntax

C#

```
public async Task<bool> IsMemberOf(params Guid[] groupIds)
{    
}
```

### Parameters

*groupIds*

Type: `guid[]`  
The group identifiers to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

//Mimic group guids
Guid[] groupIds = {
    Guid.Parse("94b53068-4501-4ea2-abbd-ba51fed5008e"),
    Guid.Parse("ec432ee4-3b15-481b-8509-faceb91e030f")
};

// Check if the user is a member of any of the array of groups
bool isSystemAdmin = await user.IsMemberOfAsync(groupIds);
```

## By group id string

Checks the user's group membership by the group identifier.

### Syntax

C#

```
public bool IsMemberOf(string groupId)
{    
}
```

### Parameters

*groupId*

Type: `string`  
The group identifier to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Check if the user is a member of the System Administrators group
bool isSystemAdmin = user.IsMemberOf("94b53068-4501-4ea2-abbd-ba51fed5008e");
```

## By group id strings

Checks the user's group membership by a list of group identifiers.

### Syntax

C#

```
public bool IsMemberOf(params string[] groupIds)
{    
}
```

### Parameters

*groupIds*

Type: `string[]`  
The group identifiers to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Check if the user is a member of any of the group identifiers
bool isInGroups = user.IsMemberOf("94b53068-4501-4ea2-abbd-ba51fed5008e", "ec432ee4-3b15-481b-8509-faceb91e030f");
```

## By group id string async

Checks the user's group membership by the group identifier asynchronously.

### Syntax

C#

```
public async Task<bool> IsMemberOfAsync(string groupId)
{    
}
```

### Parameters

*groupId*

Type: `string`  
The group identifier to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

// Check if the user is a member of the System Administrators group
bool isSystemAdmin = await user.IsMemberOfAsync("94b53068-4501-4ea2-abbd-ba51fed5008e");
```

## By group id strings async

Checks the user's group membership by a list of group identifiers asynchronously.

### Syntax

C#

```
public async Task<bool> IsMemberOfAsync(params string[] groupIds)
{    
}
```

### Parameters

*groupIds*

Type: `string[]`  
The group identifiers to check membership for.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

// Check if the user is a member of any of the group identifiers
bool isInGroups = await user.IsMemberOfAsync("94b53068-4501-4ea2-abbd-ba51fed5008e", "ec432ee4-3b15-481b-8509-faceb91e030f");
```