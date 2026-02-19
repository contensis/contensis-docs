1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 January 2022

The Metadata type is an object container for metadata that is associated with an [Entry](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry). The values contained can be any type which can be accessed as either a dynamic object or cast to a specific type.

## Properties

Name

Type

Description

Keys

ICollection<string>

A collection of the keys available

## Methods

### Get

Gets a value by the specified key and returns a dynamic object instance.

#### Syntax

C#

```
public dynamic Get(string key)
{
}
```

#### Parameters

*key*

Type: string  
The key for the data item

#### Remarks

Returns *null* if the key does not exist or if the value is null.

#### Example

C#

```
using Zengenti.Contensis.Delivery;

// Create a client
var client = ContensisClient.Create();

// Retrieve an entry
var movie = client.Entries.Get("1d1d3724-3f53-4589-8ea3-b16a1f3921f5");

// Check that a metadata item exists and access it
if (movie.Metadata.Keys.Contains("originalId"))
{
    var originalId = movie.Metadata.Get("originalId");
    // Use the value e.g render or pass into a query/search
}
```

### Get<T>

Gets a value by the specified key and returns the object instance as T.

#### Syntax

C#

```
public T Get<T>(string key)
{
}
```

#### Parameters

*T*

The type to attempt to cast the field data to.

*key*

Type: string  
The key for the data item

#### Remarks

Returns *null* if the key does not exist or if the value is null.

#### Example

C#

```
using Zengenti.Contensis.Delivery;

// Create a client
var client = ContensisClient.Create();

// Retrieve an entry
var movie = client.Entries.Get("1d1d3724-3f53-4589-8ea3-b16a1f3921f5");

// Check that a metadata item exists and access it
if (movie.Metadata.Keys.Contains("originalId"))
{
    var originalId = movie.Metadata.Get<string>("originalId");
    // Use the value e.g render or pass into a query/search
}
```