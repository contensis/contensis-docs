1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Updating a [users](/help-and-docs/apis/management-dotnet/model/user) password can be achived by calling one of the `UpdatePassword` method overloads on the user object.

-   [UpdatePassword(string existingPassword, string newPassword)](#update-password)
-   [UpdatePasswordAsync(string existingPassword, string newPassword)](#update-password-async)
-   [UpdatePassword(string newPassword)](#update-password-as-system-administrator)
-   [UpdatePasswordAsync(string newPassword)](#update-password-as-system-administrator-async)

Updating a password requires the correct existing password and a valid new password.

### Syntax

C#

```
public void UpdatePassword(string existingPassword, string newPassword)
{    
}
```

### Parameters

*existingPassword*

Type: `string`  
The user's existing password.

*newPassword*

Type: `string`  
The user's new password.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Update the password
user.UpdatePassword("d0ntT4lk4boutf1ghtClub!", "F1ghtC1ub1234!")
```

Updating a password requires the correct existing password and a valid new password.

### Syntax

C#

```
public async Task UpdatePasswordAsync(string existingPassword, string newPassword)
{    
}
```

### Parameters

*existingPassword*

Type: `string`  
The user's existing password.

*newPassword*

Type: `string`  
The user's new password.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

// Update the password
await user.UpdatePasswordAsync("d0ntT4lk4boutf1ghtClub!", "F1ghtC1ub1234!");
```

Updating a password as a system administrator only requires a new password to be specified.

### Syntax

C#

```
public void UpdatePassword(string newPassword)
{    
}
```

### Parameters

*newPassword*

Type: `string`  
The user's new password.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Update the password
user.UpdatePassword("F1ghtC1ub1234!")
```

Updating a password as a system administrator only requires a new password to be specified.

### Syntax

C#

```
public async Task UpdatePasswordAsync(string newPassword)
{    
}
```

### Parameters

*newPassword*

Type: `string`  
The user's new password.

### Examples

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = await client.Security.Users.GetAsync("t.durden");

// Update the password
await user.UpdatePasswordAsync("F1ghtC1ub1234!");
```