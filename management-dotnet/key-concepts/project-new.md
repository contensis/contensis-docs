1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

## New

Creates a new project.

### Syntax

C#

```
public Project New(string name, string id, string primaryLanguage, IList<string> supportedLanguages = null, string description = null)
{
}
```

### Parameters

*name*

Type: `string`  
The name for the project.

*id*

Type: `string`  
The id for the project.

*primaryLanguage*

Type: `string`  
The primary language for the project.

*supportedLanguages*

Type: `string`  
The name of the project.

*description*

Type: `string`  
The description for the project.

### Remarks

Throws an *ArgumentException* if the name, id or primaryLanguage parameters are either null or empty strings.

### Example

C#

```
using Zengenti.Contensis.Management;

// Create a client
var client = ManagementClient.Create();

// Create a project
var movieDbProject = client.Projects.New("Movie DB", "movieDb", "en-GB");

// Save the new project
movieDbProject.Save();
```