1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 26 April 2022

The group class represents a user group in Contensis.

## Members

Name

Type

Description

Custom

Dictionary<string,string></string,string>

The custom properties.

Description

string

A description for the group.

Name

string

The name of the group.

Type

[GroupType](/help-and-docs/apis/management-dotnet/model/grouptype)

The type of the group, 'Sys', 'Contensis', 'External'.

## Methods

Method

Returns

Description

[AddChildGroup](about:/help-and-docs/apis/management-dotnet/security/groups/add-child-group-to-a-group#add-child-group-from-a-group)

void

Adds a child group to the group.

[AddChildGroupAsync](about:/help-and-docs/apis/management-dotnet/security/groups/add-child-group-to-a-group#add-child-group-from-a-group-async)

void

Adds a child group to the group asynchronously.

[AddUser](about:/help-and-docs/apis/management-dotnet/security/groups/add-users-to-a-group#add-user-from-group)

void

Adds a user to the group.

[AddUserAsync](about:/help-and-docs/apis/management-dotnet/security/groups/add-users-to-a-group#add-user-from-group-async)

void

Adds a user to the group asynchronously.

[AddUsers](about:/help-and-docs/apis/management-dotnet/security/groups/add-users-to-a-group#add-users-from-group)

void

Adds multiple users to the group.

[AddUsersAsync](about:/help-and-docs/apis/management-dotnet/security/groups/add-users-to-a-group#add-users-from-group-async)

void

Adds multiple users to the group asynchronously.

[Children](about:/help-and-docs/apis/management-dotnet/security/groups/list-child-groups#list-with-page-options)

PagedList<[Group](/help-and-docs/apis/management-dotnet/model/group)\>

Lists the child groups for the group.

[ChildrenAsync](about:/help-and-docs/apis/management-dotnet/security/groups/list-child-groups#list-with-page-options-async)

PagedList<[Group](/help-and-docs/apis/management-dotnet/model/group)\>

Lists the child groups for the group asynchronously.

[Delete](about:/help-and-docs/apis/management-dotnet/security/groups/delete-a-group#delete)

void

Deletes the user group.

[DeleteAsync](about:/help-and-docs/apis/management-dotnet/security/groups/delete-a-group#delete-async)

void

Deletes the user group asynchronously.

[RemoveChildGroup](about:/help-and-docs/apis/management-dotnet/security/groups/remove-child-group-from-group#remove-child-group-from-group)

void

Removes a child group from the group.

[RemoveChildGroupAsync](about:/help-and-docs/apis/management-dotnet/security/groups/remove-child-group-from-group#remove-child-group-from-group-async)

void

Removes a child group from the group asynchronously.

[RemoveUser](about:/help-and-docs/apis/management-dotnet/security/groups/remove-user-from-group#remove-user-from-group)

void

Removes a user the group.

[RemoveUserAsync](about:/help-and-docs/apis/management-dotnet/security/groups/remove-user-from-group#remove-user-from-group-async)

void

Removes a user from the group asynchronously.

[Save](/help-and-docs/apis/management-dotnet/security/groups/create-and-update-groups)

void

Saves the group.

[SaveAsync](/help-and-docs/apis/management-dotnet/security/groups/create-and-update-groups)

void

Saves the group asynchronously.

[Users](about:/help-and-docs/apis/management-dotnet/security/groups/list-group-user-memberships#list-with-page-options)

void

Lists the users that are members of the group.

[UsersAsync](about:/help-and-docs/apis/management-dotnet/security/groups/list-group-user-memberships#list-with-page-options-async)

void

Lists the users that are members of the group asynchronously.