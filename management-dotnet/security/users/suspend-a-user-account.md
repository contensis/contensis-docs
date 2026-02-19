1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Security
5.  Users

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 July 2022

Suspending or Unsuspending a [user](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/user "user")'s account can be achieved by calling one of the following methods on the user object.

-   Suspend()
-   SuspendAsync()
-   Unsuspend()
-   UnsuspendAsync()

### Syntax

C#

```
public void Suspend()
{
}
```

C#

```
public async Task SuspendAsync()
{
}
```

C#

```
public void Unsuspend()
{
}
```

C#

```
public async Task UnsuspendAsync()
{
}
```

### Examples

Suspend a user synchronously.

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Suspend the user
user.Suspend();
```

Suspend a user asynchronously

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Suspend the user asynchronously
await user.SuspendAsync();
```

Unsuspend a user synchronously.

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Unsuspend the user
user.Unsuspend();
```

Unsuspend a user asynchronously.

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Get the user
User user = client.Security.Users.Get("t.durden");

// Unsuspend the user asynchronously
await user.UnsuspendAsync();
```