1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 06 September 2023

-   [Get(string fieldName)](#get)
-   [Get<T>(string fieldName)](#get-t)
-   [Set(string fieldName, object value)](#set)
-   [SetFile(string localFilePath, string filename = null)](#setfile-local-file)
-   [SetFile(Stream fileStream, string filename = null)](#setfile-stream)
-   [SetFile(byte\[\] bytes, string filename = null)](#setfile-byte-array)
-   [HasValue(string fieldName)](#hasvalue)
-   [Save()](#save)
-   [SaveAsync()](#saveasync)
-   [Delete(bool permanent = false)](#delete)
-   [DeleteAsync(bool permanent = false)](#deleteasync)
-   [NewVariation(string language)](#newvariation)
-   [Clone](#clone)
-   [CloneAsync](#cloneasync)

## Get

Gets a field from an entry by *fieldName* and returns a dynamic object instance.

### Syntax

C#

```
public dynamic Get(string fieldName)
{
}
```

### Parameters

*fieldName*

Type: string  
The name of the requested field.

### Remarks

Returns *null* if the field is not found or if the field value is null.

### Example

C#

```
// Get the title field as dynamic.
dynamic title = entry.Get("title");
```

## Get <T>

Gets a field from an entry by *fieldName* and returns a typed object instance.

### Syntax

C#

```
public T Get<T>(string fieldName)
{
}
```

### Parameters

*T*

The type to attempt to cast the field data to. The type will either be a [DataType](https://www.contensis.com/help-and-docs/apis/management-dotnet/key-concepts/data-types), a supported [DataFormat](https://www.contensis.com/help-and-docs/apis/management-dotnet/key-concepts/data-format) type or a custom type.

*fieldName*

Type: string  
The name of the requested field.

### Remarks

If the API cannot successfully cast or convert the field value then it will return the default for the specified type. Requesting field values by the wrong type will **not** result in exceptions being thrown.

### Example

C#

```
// Get the title field as defined type
string title = entry.Get<string>("title");
```

## Set

Sets data for a specified field.

### Syntax

C#

```
public void Set(string fieldName, object value)
{
}
```

### Parameters

*fieldName*

Type: string  
The name of the requested field.

*value*

Type: object  
The value for the field.

### Remarks

The type and value for the field will be validated when the entry is saved.

### Examples

C#

```
// Set a title string field value
entry.Set("title", "Star Trek - Into Darkness");

// Set a location object field value
entry.Set("filmingLocation", new Location(34.0943145, -118.3316929));

// Set an anonymous component field value
entry.Set("director",
    new
    {
        Role = "Director",
        Person = new Link("80c8e272-076e-41e0-84f4-753fc092a120")
    }
);
```

---

\## SetFile (local file)

Sets the file data for an asset instance by specifying a local file path.

### Syntax

C#

```
public void SetFile(string localFilePath, string filename = null)
{
}
```

### Parameters

*localFilePath*

Type: `string`  
The absolute path to the file.

*filename*

Type: `string`  
An optional parameter that allows the filename of the asset to be specified, overriding the name of the local file.

### Remarks

Throws an *FileNotFoundException* if the specified local file does not exist.

### Examples

C#

```
// Set new file for the asset with a filename override
entry.SetFile("c:\images\movies\batman.jpg", "Batman-returns.jpg");
```

## SetFile (Stream)

Sets the file data for an asset instance by specifying a Stream.

### Syntax

C#

```
public void SetFile(Stream fileStream, string filename = null)
{
}
```

### Parameters

*fileStream*

Type: `Stream`  
The stream containing the file bytes.

*filename*

Type: `string`  
The filename of the asset including the file extension.

### Remarks

Throws an *ArgumentException* if the stream is null or empty.

Throws an *ArgumentException* if the parentNodePath is not specified.

Throws an *ArgumentException* if the filename is null, empty or does not include a file extension.

### Examples

C#

```
// Get a file stream by downloading an image from a URL.
var stream = new HttpClient()
    .GetStreamAsync("https://en.wikipedia.org/wiki/Batman_Returns#/media/File:Batman_returns_poster2.jpg");

// Set new file for the asset with a filename override
entry.SetFile(stream, "Batman-returns.jpg");
```

## SetFile (byte array)

Sets the file data for an asset instance by specifying a byte array.

### Syntax

C#

```
public void SetFile(byte[] bytes, string filename = null)
{
}
```

### Parameters

*bytes*

Type: `byte[]`  
The file bytes.

*filename*

Type: `string`  
The filename of the asset including the file extension.

### Remarks

Throws an *ArgumentException* if the stream is null or empty.

Throws an *ArgumentException* if the parentNodePath is not specified.

Throws an *ArgumentException* if the filename is null, empty or does not include a file extension.

### Examples

C#

```
// Get a file stream by downloading an image from a URL.
var stream = new HttpClient()
    .GetStreamAsync("https://en.wikipedia.org/wiki/Batman_Returns#/media/File:Batman_returns_poster2.jpg");

// Set new file for the asset with a filename override
entry.SetFile(stream, "Batman-returns.jpg");
```

## HasValue

Determines whether the field exists and the value is not null.

### Syntax

C#

```
public bool HasValue(string fieldName)
{
}
```

### Parameters

*fieldName*

Type: string  
The name of the field to check.

### Return value

Type: boolean  
**true** if the field exists and is not null, otherwise **false**.

### Remarks

If the *fieldName* is not defined in the content type that the entry is based on then it will return false.

### Example

C#

```
if (entry.HasValue("title"))
{
    // Get the location field as type
    Location title = entry.Get<Location>("filmingLocation");
}
```

## Save

Saves an entry instance.

### Syntax

C#

```
public void Save()
{
}
```

### Return value

Type: void

### Remarks

On a successful save, the entry instance is updated with the new version details controlled from the service. An exception will be thrown if there is any issue with the save, which could be either a data validation issue, an unexpected issue in the service or a local exception.

### Example

C#

```
// Make a change to an entry.
entry.Set("title", "Forrest Gump");

try
{
    // Save the changes.
    entry.Save();
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

Saves an entry instance asynchronously.

### Syntax

C#

```
public async Task SaveAsync()
{
}
```

### Return value

Type: Task

### Remarks

On a successful save, the entry instance is updated with the new version details controlled from the service. An exception will be thrown if there is any issue with the save, which could be either a data validation issue, an unexpected issue in the service or a local exception.

### Example

C#

```
// Make a change to an entry
entry.Set("title", "Forrest Gump");

try
{
    // Save the changes asynchronously.
    entry.SaveAsnyc();
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

Delete an entry instance.

### Syntax

C#

```
public void Delete(bool permanent = false)
{
}
```

### Return value

Type: void

### Remarks

On a successful delete, the entry data is set to null.

### Example

C#

```
{
    // Delete the entry variation to the recycle bin.
    entry.Delete();
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

Delete an entry instance asynchronously.

### Syntax

C#

```
public async Task DeleteAsync(bool permanent = false)
{
}
```

### Return value

Type: Task

### Remarks

On a successful delete, the entry data is set to null.

### Example

C#

```
{
    // Delete the entry variation permanently.
    await entry.DeleteAsync(true);
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

## NewVariation

Creates a new variation of the entry for the specified language.

### Syntax

C#

```
public Entry NewVariation(string language)
{
}
```

### Parameters

*language*

Type: string  
The variation language to create.

### Return value

Type: [Entry](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/entry)  
The newly created (unsaved) entry language variation.

### Remarks

On a successful delete, the entry data is set to null.

### Example

C#

```
// Create a new french variation
var frenchVariation = entry.NewVariation("fr-FR");

// Set some data for the variation
frenchVariation.Set("title", "Belle de Jour");

// Save the new variation
frenchVariation.Save();
```

## Clone

Clones an entry with all it's variations and returns the variation language matching the entry variation it was cloned from.

### Syntax

C#

```
public Entry Clone()
{
}
```

### Return value

Type: [Entry](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/entry)  
The newly cloned entry with the language matching the entry variation that was cloned.

### Example

C#

```
// Clones an existing entry variation.
var clonedEntry = existingEntry.Clone();
```

## CloneAsync

Clones an entry with all it's variations asynchronously and returns the variation language matching the entry variation it was cloned from.

### Syntax

C#

```
public async Task<Entry> CloneAsync()
{
}
```

### Return value

Type: [Entry](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/entry)  
The newly cloned entry with the language matching the entry variation that was cloned.

### Example

C#

```
// Clones an existing entry variation asynchronously.
var clonedEntry = await existingEntry.CloneAsync();
```