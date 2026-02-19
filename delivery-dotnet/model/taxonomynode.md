1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Delivery API](/help-and-docs/apis/delivery-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 27 January 2022

The TaxonomyNode type represents a node in the taxonomy tree defined in Contensis. A TaxonomyNode can have child nodes which are automatically retrieved when the `Children` property is accessed.

## Properties

Name

Type

Description

Key

string

The key for the taxonomy node

Name

string

The name of the taxonomy node

Path

string

The full path of the taxonomy node, including the current node name

Children

IReadOnlyList<TaxonomyNode>

Child taxonomy nodes

## Example

##### Get a taxonomy node field from an entry

C#

```
using Zengenti.Contensis.Delivery;

// Create an API client
var client = ContensisClient.Create();

// Retrieve a movie by it's ID.
var movie = client.Entries.Get("3bb72e32-1fc7-4289-bf65-60a5b8ce1f78");

// Get the field value as a TaxonomyNode instance.
var movieGenre = movie.Get<TaxonomyNode>("genre");

<span>
    <!--Render the taxonomy node name-->
    @movieGenre.Name
</span>
```