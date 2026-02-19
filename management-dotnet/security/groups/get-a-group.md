1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Groups

[Log in to add to favourites](/account/login)

Page last updated 11 July 2022

Requesting an individual [group](/help-and-docs/apis/management-dotnet/model/group) can be achieved by using one of the `Get` methods overloads.

-   [Get(Guid id)](#get-by-id)
-   [GetAsync(Guid id)](#get-by-id-async)
-   [Get(string id)](#get-by-string-id)
-   [GetAsync(string id)](#get-by-string-id-async)
-   [Get(string groupName)](#get-by-group-name)
-   [GetAsync(string groupName)](#get-by-group-name-async)

Gets a group by its id.

### Syntax

C#

```
public Group Get(Guid id)
{    
}
```

### Parameters

*id*

Type: `Guid`  
The id of the group.

## Remarks

Returns *null* if no group matches the specified id.

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
```

Gets a group by its id asynchronously.

### Syntax

C#

```
public async Task<Group> GetAsync(Guid id)
{    
}
```

### Parameters

*id*

Type: `Guid`  
The id of the group.

## Remarks

Returns *null* if no group matches the specified id.

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
```

Gets a group by its id.

### Syntax

C#

```
public Group Get(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The group identifier, either group name, or identifier.

## Remarks

Returns *null* if no group matches the specified id.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the group
Group group = client.Security.Groups.Get("c5da1719-cb3f-4f2e-927b-f678293258f3");
```

Gets a group by its id asynchronously.

### Syntax

C#

```
public async Task<Group> GetAsync(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The groups identifier, either group name, or identifier.

## Remarks

Returns *null* if no group matches the specified id.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the group
Group group = await client.Security.Groups.GetAsync("c5da1719-cb3f-4f2e-927b-f678293258f3");
```

Gets a group by its name.

### Syntax

C#

```
public Group Get(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The group identifier, either group name, or identifier.

## Remarks

Returns *null* if no group matches the specified name.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the group
Group group = client.Security.Groups.Get("Fight Club Members");
```

Gets a group by its name asynchronously.

### Syntax

C#

```
public async Task<Group> GetAsync(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The groups identifier, either group name, or identifier.

## Remarks

Returns *null* if no group matches the specified group name.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the group
Group group = await client.Security.Groups.GetAsync("Fight Club Members");
```