1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 26 April 2022

The Link class represents a link to other content such as an Entry, Asset or Image. The Link class can target a specific language variation of the linked content. If a language is not specified when creating a link, then the project default is used. The DataFormat property does not need to be specified when a Link is created as it will be determined and set by the API service.

## Constructors

### Create Link with Guid id

#### Syntax

C#

```
public Link(Guid id, string language = null)
{
}
```

#### Parameters

*id*

Type: `Guid`  
The id of the entry or asset.

*language*

Type: `string` \[[LanguageCode](/help-and-docs/apis/management-dotnet/key-concepts/localization)\]  
\[Optional\] The language variation of the asset to target.

---

### Create Link with string id

#### Syntax

C#

```
public Link(string id, string language = null)
{
}
```

#### Parameters

*id*

Type: `string`  
The id of the image asset.

*language*

Type: `string` \[[LanguageCode](/help-and-docs/apis/management-dotnet/key-concepts/localization)\]  
\[Optional\] The language variation of the asset to target.

#### Properties

Name

Type

Description

Id

`Guid`

The id of the entry or asset.

Language

string \[\]

The language of the link instance.

DataFormat

string

An indicator of the link type - *entry* or *asset.*

## Examples

### Get a Link field object

C#

```
// Get the field value as a Location instance.
Link actor = movieEntry.Get<Link>("leadActor");

// Get the field value as a dynamic (ExpandoObject) instance.
dynamic actor = movieEntry.Get("leadActor");
```

### Get a list of Link field objects

C#

```
// Get the field value as a Link list.
List<Link> actors = movieEntry.Get<List<Link>>("actors");

// Alternatively get the field value as a Link array.
Link[] actors = movieEntry.Get<Link[]>("actors");
```

### Set a Link field object

C#

```
// Create a Link object targeting the default project language.
Link actor = new Link("27293124-999a-4895-afec-f060dca33508");

// Set the link value.
movieEntry.Set("leadActor", actor);
```