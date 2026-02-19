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
-   [NewChild(LocalizedString displayName)](#newchild)
-   [NewChild(LocalizedString displayName, Guid id)](#newchild-with-id)
-   [Children(string languageOrder = null)](#children)
-   [ChildrenAsync(string languageOrder = null)](#children)
-   [Parent()](#parent)
-   [ParentAsync()](#parentasync)
-   [SetChildNodeOrder(IEnumerable childOrder, string language = null)](#setchildnodeorder-with-guid-ids)
-   [SetChildNodeOrderAsync(IEnumerable childOrder, string language = null)](#setchildnodeorderasync-with-guid-ids)
-   [SetChildNodeOrder(IEnumerable childOrder, string language = null)](#setchildnodeorder-with-nodes)
-   [SetChildNodeOrderAsync(IEnumerable childOrder, string language = null)](#setchildnodeorderasync-with-nodes)
-   [DeleteChildNodeOrder(string language = null)](#deletechildnodeorder)
-   [DeleteChildNodeOrderAsync(string language = null)](#deletechildnodeorderasync)

## Save

Saves a node instance.

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
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

// Update a value.
node.Slug = "iron-man";

try
{
    // Save the changes.
    node.Save();
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

Saves a node instance asynchronously.

### Syntax

C#

```
public async Task SaveAsync()
{
}
```

### Return value

Type: `Task`

### Remarks

An exception will be thrown if there is any issue with the save, which could be either a data validation issue, an unexpected issue in the service or a local exception.

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

// Update a value.
node.Slug = "iron-man";

try
{
    // Save the changes asynchronously.
    await node.SaveAsnyc();
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

Deletes a node instance.

### Syntax

C#

```
public void Delete()
{
}
```

### Return value

Type: `void`

### Remarks

On a successful delete, the node data is set to null.

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Delete the node instance.
    node.Delete();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## DeleteAsync

Delete a entry node asynchronously.

### Syntax

C#

```
public async Task DeleteAsync()
{
}
```

### Return value

Type: `Task`

### Remarks

On a successful delete, the node data is set to null.

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Delete the node instance.
    await node.DeleteAsync();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## NewChild

Creates and returns a new child node with the current node set as the parent.

### Syntax

C#

```
public Node NewChild(LocalizedString displayName)
{
}
```

### Parameters

*displayName*

Type: `string`  
The display name of the node.

### Return value

### Remarks

An `InvalidOperationException` is thrown if the current node has not been committed.

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Create a new node instance from an existing parent.
    var childNode = node.NewChild("Batman Returns");

    // Set some additional properties.
    childNode.Slug = "batman-returns";
    childNode.EntryId = Guid.Parse("f91e37bd-0cf4-4631-b22a-eb0b78841f23");

    // Commit the newly created child node.
    childNode.Save();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## NewChild with id

Creates and returns a new child node with the current node set as the parent and the specified id.

### Syntax

C#

```
public Node NewChild(LocalizedString displayName, Guid id)
{
}
```

### Parameters

*displayName*

Type: `string`  
The display name of the node.

*id*

Type: `Guid`  
The id to be set for the new node.

### Return value

### Remarks

An `InvalidOperationException` is thrown if the current node has not been committed.

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Create a new node instance from an existing parent.
    var childNode = node.NewChild("Batman Returns", nodeGuid);

    // Set some additional properties.
    childNode.Slug = "batman-returns";
    childNode.EntryId = Guid.Parse("f91e37bd-0cf4-4631-b22a-eb0b78841f23");

    // Commit the newly created child node.
    childNode.Save();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## Children

Gets the child nodes for the current node.

### Syntax

C#

```
public List<Node> Children(string languageOrder = null)
{
}
```

### Parameters

*languageOrder*

Type: `string`  
An optional parameter to specific which language order the nodes should be returned.

### Return value

Type: `List<Node>`

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the child nodes in the order specified for french.
    var childNodes = node.Children("fr-FR");

    foreach(var child in childNodes)
    {
        // perform actions on the child nodes.
    }
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## ChildrenAsync

Gets the child nodes for the current node asynchronously.

### Syntax

C#

```
public async Task<List<Node>> ChildrenAsync(string languageOrder = null)
{
}
```

### Parameters

*languageOrder*

Type: `string`  
An optional parameter to specific which language order the nodes should be returned.

### Return value

Type: `Task<List<Node>>`

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the child nodes for the node.
    var childNodes = await node.ChildrenAsync();

    foreach(var child in childNodes)
    {
        // perform actions on the child nodes.
    }
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## Parent

Gets the parent node for the current node.

### Syntax

C#

```
public Node Parent()
{
}
```

### Return value

Type: `Node`

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the parent node for the node.
    var parent = node.Parent();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## ParentAsync

Gets the parent node for the current node asynchronously.

### Syntax

C#

```
public async Task<Node> ParentAsync()
{
}
```

### Return value

Type: `Task<Node>`

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the parent node for the node.
    var parent = await node.ParentAsync();
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## SetChildNodeOrder with Guid ids

Sets the child node order for the current node.

### Syntax

C#

```
public void SetChildNodeOrder(IEnumerable<Guid> childOrder, string language = null)
{
}
```

### Parameters

*childOrder*

Type: `IEnumerable<Guid>`  
An ordered list of nodes ids.

*language*

Type: `string`  
An optional parameter to specify which language the order is for.

### Return value

Type: void

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the child nodes for the node.
    var childNodes = node.Children();

    // Order the nodes by the French display name in a descending order and select the ids.
    var orderedNodeIds = childNodes.OrderByDescending(c => c.DisplayName["fr-FR"]).Select(c => c.Id.Value);

    // Set the node order for French.
    nodes.SetChildNodeOrder(orderedNodeIds, "fr-FR");
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## SetChildNodeOrderAsync with Guid ids

Sets the child node order for the current node.

### Syntax

C#

```
public async Task SetChildNodeOrderAsync(IEnumerable<Guid> childOrder, string language = null)
{
}
```

### Parameters

*childOrder*

Type: `IEnumerable<Guid>`  
An ordered list of nodes ids.

*language*

Type: `string`  
An optional parameter to specify which language the order is for.

### Return value

Type: Task

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the child nodes for the node.
    var childNodes = await node.ChildrenAsync();

    // Order the nodes by the French display name in a descending order and select the ids.
    var orderedNodeIds = childNodes.OrderByDescending(c => c.DisplayName["fr-FR"]).Select(c => c.Id.Value);

    // Set the node order for French.
    await nodes.SetChildNodeOrderAsync(orderedNodeIds, "fr-FR");
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## SetChildNodeOrder with nodes

Sets the child node order for the current node.

### Syntax

C#

```
public void SetChildNodeOrder(IEnumerable<Node> childOrder, string language = null)
{
}
```

### Parameters

*childOrder*

Type: `IEnumerable<Node>`  
An ordered list of nodes.

*language*

Type: `string`  
An optional parameter to specify which language the order is for.

### Return value

Type: void

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the child nodes for the node.
    var childNodes = node.Children();

    // Order the nodes by the French display name in a descending order.
    var orderedNodes = childNodes.OrderByDescending(c => c.DisplayName["fr-FR"]);

    // Set the node order for French.
    nodes.SetChildNodeOrder(orderedNodes, "fr-FR");
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## SetChildNodeOrderAsync with nodes

Sets the child node order for the current node.

### Syntax

C#

```
public async Task SetChildNodeOrderAsync(IEnumerable<Node> childOrder, string language = null)
{
}
```

### Parameters

*childOrder*

Type: `IEnumerable<Node>`  
An ordered list of nodes.

*language*

Type: `string`  
An optional parameter to specify which language the order is for.

### Return value

Type: Task

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Get the child nodes for the node.
    var childNodes = await node.ChildrenAsync();

    // Order the nodes by the French display name in a descending order.
    var orderedNode = childNodes.OrderByDescending(c => c.DisplayName["fr-FR"]);

    // Set the node order for French.
    await nodes.SetChildNodeOrderAsync(orderedNode, "fr-FR");
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## DeleteChildNodeOrder

Deletes the child node order for the current node.

### Syntax

C#

```
public void DeleteChildNodeOrder(string language = null)
{
}
```

### Parameters

*language*

Type: `string`  
An optional parameter to specify which language to delete the order for.

### Return value

Type: void

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Delete the default node order.
    nodes.DeleteChildNodeOrder();

    // Delete the node order for German.
    nodes.DeleteChildNodeOrder("de-DE");
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```

## DeleteChildNodeOrderAsync

Deletes the child node order for the current node.

### Syntax

C#

```
public async Task DeleteChildNodeOrderAsync(string language = null)
{
}
```

### Parameters

*language*

Type: `string`  
An optional parameter to specify which language to delete the order for.

### Return value

Type: Task

### Example

C#

```
// Get a node.
var node = client.Nodes.Get("1abf0e7f-7507-4578-a3be-1280ed7486fe");

try
{
    // Delete the default node order.
    await nodes.DeleteChildNodeOrderAsync();

    // Delete the node order for German.
    await nodes.DeleteChildNodeOrderAsync("de-DE");
}
catch(RestRequestException restEx)
{
    // Handle service error.
}
catch(Exception ex)
{
    // Handle anything else, e.g. network error.
}
```