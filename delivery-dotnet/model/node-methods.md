## Children

Gets the child nodes for the current node.

### Syntax

C#

```
public IReadonlyList<Node> Children(IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Example

C#

```
// Get the child nodes for the current node.
IReadonlyList<Node> childNodes = currentNode.Children();
```

## ChildrenAsync

Gets the child nodes for the current node asynchronously.

### Syntax

C#

```
public Task<IReadonlyList<Node>> ChildrenAsync(IList<string> entryFields = null, entryLinkDepth = 0,  Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Example

C#

```
// Get the child nodes for the current node.
IReadonlyList<Node> childNodes = await currentNode.ChildrenAsync();
```

## Parent

Gets the parent node for the current node.

### Syntax

C#

```
public Node Parent(IList<string> entryFields = null, entryLinkDepth = 0,
            Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Remarks

Consider using ParentId if that is all is required to avoid unnecessary network calls.

### Example

C#

```
// Get the child nodes for the current node.
Node parentNode = currentNode.Parent();
```

## ParentAsync

Gets the parent node for the current node asynchronously.

### Syntax

C#

```
public Node ParentAsync(IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Remarks

Consider using ParentId if that is all is required to avoid unnecessary network calls.

### Example

C#

```
// Get the parent node for the current node.
Node parentNode = await currentNode.ParentAsync();
```

## AncestorAtLevel

Gets the ancestor at the specified level.

### Syntax

C#

```
public Node AncestorAtLevel(int level, IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*level*

Type: `int`  
The level in the tree of the ancestor to return

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Remarks

If a level is specified that is equal to or greater than the level of the current node then *null* will be returned.

### Example

C#

```
// Get the ancestor node at level 2
Node ancestorNode = currentNode.AncestorAtLevel(2);
```

## AncestorAtLevelAsync

Gets the ancestor node at the specified level.

### Syntax

C#

```
public async Task<Node> AncestorAtLevelAsync(int level, IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*level*

Type: `int`  
The level in the tree of the ancestor to return

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Remarks

If a level is specified that is equal to or greater than the level of the current node then *null* will be returned.

### Example

C#

```
// Get the ancestor node at level 2
Node ancestorNode = await currentNode.AncestorAtLevelAsync(2);
```

## Ancestors

Gets the ancestor nodes for a node with an optional start level.

### Syntax

C#

```
public IReadonlyList<Node> Ancestors(int startLevel = 0, IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*startLevel*

Type: `int`  
The level to start returning the ancestors from

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Remarks

If a level is specified that is equal to or greater than the level of the current node then an empty list will be returned.

### Example

C#

```
// Get the ancestors nodes starting at level 2
IReadonlyList<Node> ancestorNodes = currentNode.Ancestors(2);

// Create a breadcrumb component from the list...
```

## AncestorsAsync

Gets the ancestor nodes for a node asynchronously with an optional start level.

### Syntax

C#

```
public async Task<IReadonlyList<Node>> AncestorsAsync(int startLevel = 0, IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*startLevel*

Type: `int`  
The level to start returning the ancestors from

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Remarks

If a level is specified that is equal to or greater than the level of the current node then an empty list will be returned.

### Example

C#

```
// Get the ancestors nodes starting at level 2
IReadonlyList<Node> ancestorNodes = await currentNode.AncestorsAsync(2);

// Create a breadcrumb component from the list...
```

## Siblings

Gets the sibling nodes for a node including the current node.

### Syntax

C#

```
public IReadonlyList<Node>> Siblings(IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Example

C#

```
// Get the sibling nodes
IReadonlyList<Node> siblingNodes = currentNode.Siblings();
```

## SiblingsAsync

Gets the sibling nodes for a node asynchronously including the current node.

### Syntax

C#

```
public async Task<IReadonlyList<Node>> SiblingsAsync(IList<string> entryFields = null, entryLinkDepth = 0, Dictionary<string, int> entryFieldLinkDepths = null)
{
}
```

### Parameters

*entryFields*

Type: `IList<string>`  
The fields to include for the entry (if attached) and any of it's linked entries if an entryLinkDepth value is included.

*entryLinkDepth*

Type: `int`  
The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10.

By default, no entry data is resolved for linked entries. **Please note:** Only fields which are specified in the *entryFields* parameter will be resolved.

*entryFieldLinkDepths* (version 16+ only)

Type: `Dictionary<string, int>`The depth at which to resolve the full entry data for a linked entry, specified by field path, with a maximum depth value of 10 - larger values will be handled as being 10. Field paths are dot-delimited (such as "composer.component.entryLinkField") and the longest applicable path is used. If no matching path is found then the linkDepth is used.

By default, no entry data is resolved for linked entries. **Please note:** You can only resolve fields which are specified in the *entryFields* parameter.

### Example

C#

```
// Get the siblings nodes
IReadonlyList<Node> siblingNodes = await currentNode.SiblingsAsync();
```

## Entry

Gets the entry instance if one has been assigned. The language for the entry will match the language of the node.

### Syntax

C#

```
public Entry Entry()
{
}
```

### Remarks

Will return *null* if an entry is not assigned, the associated entry does not exist or if the entry has not be published and the current version status is published. If the entry has not already been resolved then it will be auto-resolved when the method is invoked.

### Example

C#

```
// Get the associated entry
Entry entry = currentNode.Entry();
```

## EntryAsync

Gets the entry instance asynchronously if one has been assigned. The language for the entry will match the language of the node.

### Syntax

C#

```
public async Task<Entry> Entry()
{
}
```

### Remarks

Will return *null* if an entry is not assigned, the associated entry does not exist or if the entry has not be published and the current version status is published. If the entry has not already been resolved then it will be auto-resolved when the method is invoked.

### Example

C#

```
// Get the associated entry only including the fields I want
Entry movie = await currentNode.EntryAsync();
```

## Entry<T>

Gets the entry instance as a [typed model](/help-and-docs/apis/delivery-dotnet/key-concepts/typed-models "typed-models") if one has been assigned. The language for the entry will match the language of the node.

### Syntax

C#

```
public T Entry<T>()
{
}
```

### Remarks

Will return *null* if an entry is not assigned, the associated entry does not exist or if the entry has not be published and the current version status is published. If the entry has not already been resolved then it will be auto-resolved when the method is invoked.

### Example

C#

```
public class Movie: EntryModel
{
    public string Title { get; set; }

    public string Synopsis { get; set; }

    public int ReleaseYear { get; set; }
}


// Get the associated entry only including the fields I want
Movie movie = currentNode.Entry<Movie>();
```

## EntryAsync<T>

Gets the entry instance as a [typed model](/help-and-docs/apis/delivery-dotnet/key-concepts/typed-models "typed-models") asynchronously if one has been assigned. The language for the entry will match the language of the node.

### Syntax

C#

```
public async Task<T> Entry<T>()
{
}
```

### Remarks

Will return *null* if an entry is not assigned, the associated entry does not exist or if the entry has not be published and the current version status is published. If the entry has not already been resolved then it will be auto-resolved when the method is invoked.

### Example

C#

```
public class Movie: EntryModel
{
    public string Title { get; set; }

    public string Synopsis { get; set; }

    public int ReleaseYear { get; set; }
}


// Get the associated entry only including the fields I want
Movie movie = await currentNode.EntryAsync<Movie>();
```