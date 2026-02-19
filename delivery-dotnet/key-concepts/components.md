1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Delivery API](/help-and-docs/apis/delivery-dotnet)
4.  Key concepts

[Log in to add to favourites](/account/login)

Page last updated 26 January 2022

Components are structures that are defined in the Component editor as custom types. They can be added as field types to [Content Types](/help-and-docs/apis/delivery-dotnet/model/contenttype) as entry-level fields or as [ComposedField](/help-and-docs/apis/delivery-dotnet/model/composed) items. Components themselves can contain any field types except other components or ComposedField types.

## Getting component data

Accessing component data from either an entry-level field or from a ComposedFieldItem instance can be done by either providing a user-defined type as a generic type parameter to specify the return type or alternatively using the non-generic method to return a `dynamic` object instance.

When a component is accessed that contains either Entry, Asset or Image links, then the links are resolved at the point of first access.

Consider the following user-defined type that matches a component:

C#

```
using Zengenti.Contensis.Delivery;

public class MovieRole: ComponentModel
{
    public string RoleName { get; set; }

    public string Description { get; set; }

    public Entry Person => Resolve<Entry>("person");
}
```

Accessing the data from an Entry is done in the same way any other field data is accessed.

C#

```
// Access the director field data using the generic type
MovieRole directorRole = movieEntry.Get<MovieRole>("director");

// The Person entry is fully resolved
Entry director = directorRole.Person;
```

C#

```
// Alternatively return a dynamic object
dynamic directorRole = movieEntry.Get("director");

// The Person entry is fully resolved
Entry director = directorRole.Person;
```

The same applies when accessing a list of components:

C#

```
// Access the actors field data using the generic type
List<MovieRole> actorRoles = movieEntry.Get<List<MovieRole>>("actors");

foreach(MovieRole role in actorRoles)
{
    // The Person entry is fully resolved
    var actorName = role.Person.Get<string>("name");
}
```

More information around the use of ComponentModel [can be found on the TypedModel page](about:/help-and-docs/apis/delivery-dotnet/key-concepts/typed-models#entrymodel--componentmodel-base-classes).