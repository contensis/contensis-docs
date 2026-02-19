1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Requesting an individual [user](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/user) can be achieved by using one of the `Get` methods overloads.

-   [Get(Guid id)](#get-by-id)
-   [GetAsync(Guid id)](#get-by-id-async)
-   [Get(string id)](#get-by-string-id)
-   [GetAsync(string id)](#get-by-string-id-async)
-   [Get(string username)](#get-by-username)
-   [GetAsync(string username)](#get-by-username-async)
-   [Get(string emailAddress)](#get-by-email-address)
-   [GetAsync(string emailAddress)](#get-by-email-address-async)

Gets a user by its identifier.

### Syntax

C#

```
public User Get(Guid id)
{    
}
```

### Parameters

*id*

Type: `Guid`  
The id of the user.

## Remarks

Returns *null* if no user matches the specified id.

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
```

Gets a user by its identifier asynchronously.

### Syntax

C#

```
public async Task<User> GetAsync(Guid id)
{    
}
```

### Parameters

*id*

Type: `Guid`  
The id of the user.

## Remarks

Returns *null* if no user matches the specified id.

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
```

Gets a user by its id identifier.

### Syntax

C#

```
public User Get(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The users identifier, either username, email address, or id.

## Remarks

Returns *null* if no user matches the specified id.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("c5da1719-cb3f-4f2e-927b-f678293258f3");
```

Gets a user by its id identifier asynchronously.

### Syntax

C#

```
public async Task<User> GetAsync(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The users identifier, either username, email address, or id.

## Remarks

Returns *null* if no user matches the specified id.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("c5da1719-cb3f-4f2e-927b-f678293258f3");
```

Gets a user by their username identifier.

### Syntax

C#

```
public User Get(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The users identifier, either username, email address, or id.

## Remarks

Returns *null* if no user matches the specified username.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("r.paulsen");
```

Gets a user by their username identifier asynchronously.

### Syntax

C#

```
public async Task<User> GetAsync(string id)
{    
}
```

### Parameters

*id*

Type: `string`  
The users identifier, either username, email address, or id.

## Remarks

Returns *null* if no user matches the specified username.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("r.paulsen");
```

Gets a user by their email address.

### Syntax

C#

```
public User Get(string id)
{    
}
```

### Parameters

*username*

Type: `string`  
The users identifier, either username, email address, or id.

## Remarks

Returns *null* if no user matches the specified email address.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("robert.paulsen@fightclub.com")
```

Gets a user by their email address asynchronously.

### Syntax

C#

```
public async Task<User> GetAsync(string id)
{    
}
```

### Parameters

*username*

Type: `string`  
The users identifier, either username, email address, or id.

## Remarks

Returns *null* if no user matches the specified email address.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("robert.paulsen@fightclub.com");
```