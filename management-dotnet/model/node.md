1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 27 April 2022

A node represents a location within the navigational structure of a website. The linking of nodes as parent-child relationships forms the hierarchical structure of a website, with a node having a single parent and (optionally) multiple child nodes. A single entry can optionally be assigned to a node.

## Properties

Name

Type

Description

Id

Guid

The node identifier.

ProjectId

string

The project identifier.

ParentId

Guid?

The parent node id. The value will be null if the node is the root.

DisplayName

LocalizedString

The localized node display name.

Slug

LocalizedString

The localized node slug.

EntryId

Guid?

(Optional) The associated entry identifier.

ChildCount

int

The count of child nodes.

IsCanonical

boolean

A flag to indicate whether the node represents the canonical path for the attached entry.

IncludeInMenu

boolean

A flag to indicate whether the node is to be included in menus.

## Methods

Method

Returns

Description

[Save()](about:/help-and-docs/apis/management-dotnet/model/node-methods#save)

void

Saves changes made to the node instance.

[SaveAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#saveasync)

Task

Saves changes made to the node instance asynchronously.

[Delete()](about:/help-and-docs/apis/management-dotnet/model/node-methods#delete)

void

Deletes the node instance.

[DeleteAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#deleteasync)

Task

Deletes the node instance instance asynchronously.

[NewChild(LocalizedString displayName)](about:/help-and-docs/apis/management-dotnet/model/node-methods#newchild)

Node

Creates and returns a new child node by specifying the display name.

[NewChild(LocalizedString displayName, Guid id)](about:/help-and-docs/apis/management-dotnet/model/node-methods#newchild-with-id)

Node

Creates and returns a new child node by specifying the display name and id.

[Children()](about:/help-and-docs/apis/management-dotnet/model/node-methods#children)

List<Node>

Gets the child nodes for the current node.

[ChildrenAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#childrenasync)

Task<List<Node>>

Gets the child nodes for the current node asynchronously.

[Parent()](about:/help-and-docs/apis/management-dotnet/model/node-methods#parent)

Node

Gets the parent node for the current node.

[ParentAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#parentasync)

Node

Gets the parent node for the current node asynchronously.

[SetChildNodeOrder()](about:/help-and-docs/apis/management-dotnet/model/node-methods#setchildnodeorder-with-guid-ids)

void

Sets the child node order for the current node.

[SetChildNodeOrderAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#setchildnodeorderasync-with-guid-ids)

Task

Sets the child node order for the current node asynchronously.

[SetChildNodeOrder()](about:/help-and-docs/apis/management-dotnet/model/node-methods#setchildnodeorder-with-nodes)

void

Sets the child node order for the current node.

[SetChildNodeOrderAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#setchildnodeorderasync-with-nodes)

Task

Sets the child node order for the current node asynchronously.

[DeleteChildNodeOrder()](about:/help-and-docs/apis/management-dotnet/model/node-methods#deletechildnodeorder)

void

Deletes the child node order for the current node.

[DeleteChildNodeOrderAsync()](about:/help-and-docs/apis/management-dotnet/model/node-methods#deletechildnodeorderasync)

Task

Deletes the child node order for the current node asynchronously.