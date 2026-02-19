1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 April 2022

-   [Save()](#save)
-   [SaveAsync()](#saveasync)
-   [Delete()](#delete)
-   [DeleteAsync()](#deleteasync)

## Save

Saves a project instance.

### Syntax

C#

```
public void Save()
{
}
```

### Return value

Type: `void`

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client.
var client = ManagementClient.Create();

// Get a specific project.
var project = client.Projects.Get("movieDb");

// Make a change to the project.
project.Description = "Movie database project";

try
{
    // Save the changes.
    project.Save();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(ValidationException valEx)
{
    // Handle data validation errors.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## SaveAsync

Saves a project instance asynchronously.

### Syntax

C#

```
public Task SaveAsync()
{
}
```

### Return value

Type: `Task`

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client.
var client = ManagementClient.Create();

// Get a specific project.
var project = client.Projects.Get("movieDb");

// Make a change to the project.
project.Description = "Movie database project";

try
{
    // Save the changes.
    await project.SaveAsync();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(ValidationException valEx)
{
    // Handle data validation errors.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## Delete

Deletes a project instance.

### Syntax

C#

```
public void Delete()
{
}
```

### Return value

Type: `void`

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client.
var client = ManagementClient.Create();

// Get a specific project.
var project = client.Projects.Get("movieDb");

try
{
    // Delete the instance.
    project.Delete();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(ValidationException valEx)
{
    // Handle data validation errors.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## DeleteAsync

Deletes a project instance asynchronously.

### Syntax

C#

```
public Task DeleteAsync()
{
}
```

### Return value

Type: `Task`

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client.
var client = ManagementClient.Create();

// Get a specific project.
var project = client.Projects.Get("movieDb");

try
{
    // Delete the instance.
    await project.DeleteAsync();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(ValidationException valEx)
{
    // Handle data validation errors.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```