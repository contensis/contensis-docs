1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Deploying websites and apps](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps)
4.  Site View

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 28 May 2024

Site View Permissions can be configured by any System Administrator or Roles Administrator in Contensis. There is also a security group called Site View Administrators that grants members the ability manage any node in the Site View tree without them needing to be assigned to a role.

This article outlines the available properties and some example role scenarios.

The following properties can be set when adding a Site View permission to a role:

## Location

The location property determines the starting Site View location where permissions are to be set.

## Scope

The scope property determines the node or nodes to which the permission set applies. They are broken down in to the following scopes:

Scope

Description

Selected node and descendants

The permission set is applied to the selected node, determined by the location property and any descendant within that node. For example, the `/about-us/` node and its descendants `/about-us/values` and `/about-us/our-company`.

Selected node

The permission set is applied to the selected node only and has no effect on any child or descendant nodes. For example, only the `/about-us/` node.

Descendants

The permission set only applies to descendants of the selected node. For example, nodes inside the `/about-us/` section such as `/about-us/values` and `/about-us/our-company`, but not `/about-us/` itself.

## Actions

Action

Description

Create node

The ability to create a child node.

Update node

The ability to update the properties of a node, including the *Display name*, *Slug* and *Include in menu* properties.

Delete node

The ability to delete a node.

Move node

The ability to move a node to a new location. When moving a node, a user will also need permission to create nodes in the destination the node is being moved to.

Update renderer

The ability to change the renderer attached to a node.

Update proxy

The ability to change or attach a proxy to a node through the proxy editor.

Manage child order

The ability to change the order of nodes within a section of the Site View tree. This normally applies to the descendants of a selected node.

Manage entries

The ability to add, attach, detach or replace entries on a node within the Site View tree. Either all content types or a specific set of content types need to be assigned to the manage entry permission to control what content can be placed on a node.

## Example 1: Create and manage plants in `/products/plant/`

As a system administrator, I want my product editors to only create new plants inside `/products/plant/`.

![](/image-library/resources-images/user-guides-images/site-view-permissions-plant.x1e7367b0.png?q=80&f=webp)

### Entries

Example 1: Entry permissions

Actions

Content type

All actions

Plant

### Site View

Example 1: Site View permissions

Path

Scope

Actions

`products/plant/`

Selected node

Create

`products/plant/`

Descendants

Update nodes, Manage entries of the `Plant` content type

## Example 2: Create content or landing pages in the about section

As a system administrator, I want my marketing team to be able to create landing pages and content pages in the `/about/` section.

![](/image-library/resources-images/user-guides-images/site-view-permissions-marketing-team-about.x74c7fcfa.png?q=80&f=webp)

### Entries

Example 2: Entry permissions

Actions

Content type

All actions

Content page

All actions

Landing page

### Site View

Example 2: Site View permissions

Path

Scope

Actions

`/about/`

Selected node

Create

`/about/`

Descendants only

Update node, Manage entries of `Content page` and `Landing page` content types

## Example 3: Update or replace homepage

As a system administrator, I want my marketing team to be able to update the existing homepage or replace the existing homepage for our site.

![](/image-library/resources-images/user-guides-images/site-view-permissions-marketing-team-homepage.x9143992c.png?q=80&f=webp)

### Entries

Example 3: Entry permissions

Actions

Content type

Update node, Submit / Revoke

Homepage

### Site View

Example 3: Site View permissions

Path

Scope

Actions

`/`

Selected node

Manage entries of the `Homepage` content type