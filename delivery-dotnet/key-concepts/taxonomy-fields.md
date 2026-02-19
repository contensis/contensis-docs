1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Fields defined as a taxonomy field (DataType = String, DataFormat = taxonomy) are automatically resolved in the Delivery API and returned as [TaxonomyNode](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/taxonomynode) instances. A TaxonomyNode has a name, a path and child nodes.

The following example shows how a taxonomy node can be retrieved from an [Entry](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry).

C#

```
// Create a client
var client = ContensisClient.Create();

// Get an entry
var movie = client.Entries.Get("c68054c1-6ce8-4e9c-94d3-3d8332c85352");

// Get the field value as a taxonomy node
var genreNode = movie.Get<TaxonomyNode>("genre");
```

If a taxonomy node instance has child nodes, then they can be accessed using the Children property of the node. The child nodes are auto-resolved from the service.

C#

```
// Accessing the Children property resolves the child nodes
<ul>
@foreach(var node in genreNode.Children)
{
   <li>@node.Name</li> 
}
</ul>
```