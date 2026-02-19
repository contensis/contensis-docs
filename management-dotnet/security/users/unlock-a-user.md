1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](/account/login)

Page last updated 06 December 2020

If a user account has been locked by an administrator or from too many incorrect password attempts, the account can be unlocked by calling

-   Unlock
-   UnlockAsync

### Syntax

C#

```
public void Unlock()
{   
}
```

C#

```
public async Task UnlockAsync()
{   
}
```

### Examples

Unlock a user.

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Unlock the user
user.Unlock();
```

Unlock a user asynchronously.

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Unlock the user asynchronously
await user.UnlockAsync();
```