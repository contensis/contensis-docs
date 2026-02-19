1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Delivery API](/help-and-docs/apis/delivery-dotnet)
4.  Key concepts

[Log in to add to favourites](/account/login)

Page last updated 22 January 2024

Requesting an individual entry can be achieved by using one of the `Get` method overloads.

-   [Get(Guid id, string language, int linkDepth, IList fields, Dictionary<string, int> fieldLinkDepths)](#get-by-guid-id)
-   [Get<T>(Guid id, string language, int linkDepth, IList fields](#get-typed-model-by-guid-id)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-typed-model-by-guid-id)
-   [Get(string id, string language, int linkDepth, IList fields](#get-by-string-id)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-by-string-id)
-   [Get<T>(string id, string language, int linkDepth, IList fields](#get-typed-model-by-string-id)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-typed-model-by-string-id)
-   [GetAsync(Guid id, string language, int linkDepth, IList fields](#get-by-guid-id-async)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-by-guid-id-async)
-   [GetAsync<T>(Guid id, string language, int linkDepth, IList fields](#get-typed-model-by-guid-id-async)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-typed-model-by-guid-id-async)
-   [GetAsync(string id, string id, int linkDepth, IList fields](#get-by-string-id-async)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-by-string-id-async)
-   [GetAsync<T>(string id, string id, int linkDepth, IList fields](#get-typed-model-by-string-id-async)[, Dictionary<string, int> fieldLinkDepths](#get-by-guid-id)[)](#get-typed-model-by-string-id-async)

## Get by Guid id

Gets an entry by its `Guid` identifier.

### Syntax

C#

```
public Entry Get(Guid id, string language = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null)
{
}
```

### Parameters

*id*

Type: `Guid`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, with a maximum depth value of 10 - larger values will be handled as being 10. By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist.

### Examples

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Entry movie = client.Entries.Get(movieGuid, "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get typed model by Guid id

Gets a typed entry model by its `Guid` identifier.

### Syntax

C#

```
public T Get<T>(Guid id, string language = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths) where T: class
{
}
```

### Parameters

*T*

The model class, either a plain class or inheriting from EntryModel.

*id*

Type: `Guid`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, with a maximum depth value of 10 - larger values will be handled as being 10. By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist.

### Examples

C#

```
public class Movie
{
    public string Title { get; set; }

    public DateTime DateOfRelease { get; set; }
}
```

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Movie movie = client.Entries.Get<Movie>(movieGuid, "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get by string id

Gets an entry by its identifier.

### Syntax

C#

```
public Entry Get(string id, string languageCode = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null)
{
}
```

### Parameters

*id*

Type: `string`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, with a maximum depth value of 10 - larger values will be handled as being 10. By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist. If the id string is not a valid `Guid` format then an exception will be thrown.

### Examples

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Entry movie = client.Entries.Get("456e5f2a-a1cf-4520-a46c-e5f22ed299e8", "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get typed model by string id

Gets a typed entry model by its identifier.

### Syntax

C#

```
public T Get<T>(string id, string languageCode = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null) where T: class
{
}
```

### Parameters

*T*

The model class, either a plain class or inheriting from EntryModel.

*id*

Type: `string`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, with a maximum depth value of 10 - larger values will be handled as being 10. By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist. If the id string is not a valid `Guid` format then an exception will be thrown.

### Examples

C#

```
public class Movie
{
    public string Title { get; set; }

    public DateTime DateOfRelease { get; set; }
}
```

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Movie movie = client.Entries.Get<Movie>("456e5f2a-a1cf-4520-a46c-e5f22ed299e8", "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get by Guid id async

Gets an entry by its `Guid` identifier asynchronously.

### Syntax

C#

```
public async Task<Entry> GetAsync(Guid id, string language = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null)
{
}
```

### Parameters

*id*

Type: `Guid`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, with a maximum depth value of 10 - larger values will be handled as being 10. By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist.

### Examples

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Entry movie = await client.Entries.GetAsync(movieGuid, "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get typed model by Guid id async

Gets a typed model by its `Guid` identifier asynchronously.

### Syntax

C#

```
public async Task<T> GetAsync<T>(Guid id, string language = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null) where T: class
{
}
```

### Parameters

*T*

The model class, either a plain class or inheriting from EntryModel.

*id*

Type: `Guid`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, with a maximum depth value of 10 - larger values will be handled as being 10. By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist.

### Examples

C#

```
public class Movie
{
    public string Title { get; set; }

    public DateTime DateOfRelease { get; set; }
}
```

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry as a Movie type, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Movie movie = await client.Entries.GetAsync<Movie>(movieGuid, "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get by string id async

Gets an entry by its `string` identifier asynchronously.

### Syntax

C#

```
public async Task<Entry> GetAsync(string id, string language = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null)
{
}
```

### Parameters

*id*

Type: `string`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry. The max depth that can be specified is 10 - larger values will be handled as being 10. By default, no entry data is resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist. If the id string is not a valid `Guid` format then an exception will be thrown.

### Examples

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Entry movie = await client.Entries.GetAsync("456e5f2a-a1cf-4520-a46c-e5f22ed299e8", "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```

## Get typed model by string id async

Gets an entry by its `string` identifier asynchronously.

### Syntax

C#

```
public async Task<T> GetAsync<T>(string id, string language = null, int linkDepth = 0, IList<string> fields = null, Dictionary<string, int> fieldLinkDepths = null) where T: class
{
}
```

### Parameters

*T*

The model class, either a plain class or inheriting from EntryModel.

*id*

Type: `string`  
The id of the entry.

*language*

Type: `string`  
The specified language variation for the entry. If no value is provided then the project default language is used.

*linkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry. The max depth that can be specified is 10 - larger values will be handled as being 10. By default, no entry data is resolved.

*fields*

Type: `IList<string>`  
The list of fields to include in the entry. By default, all fields are returned.

*fieldLinkDepths* (requires version 16+)

Type: `Dictionary<string, int>`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** linked assets are always fully resolved.

### Remarks

Returns *null* if an entry with an id matching the specified id does not exist. If the id string is not a valid `Guid` format then an exception will be thrown.

### Examples

C#

```
public class Movie
{
    public string Title { get; set; }

    public DateTime DateOfRelease { get; set; }
}
```

C#

```
// Create a client
var client = ContensisClient.Create();

// Get the french variation of the movie entry as a Movie type, returning just the title and resolving links to a depth of 3, except for the entryLink fields which resolves to a depth of 2 and the relatedItems component in the composer field, which resolves to a depth of 1
Movie movie = await client.Entries.GetAsync<Movie>("456e5f2a-a1cf-4520-a46c-e5f22ed299e8", "fr-fr", 3, new[] {"title"}, new Dictionary<string, int>{{"entryLink", 2}, {"composer.relatedItems", 1}});
```