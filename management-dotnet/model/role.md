1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 April 2022

Role definitions in the Management API contain permissions associated with entries and assets, with users, groups and API keys assigned to those permissions.

## Properties

Name

Type

Description

Id

Guid

The role identifier.

Name

string

The role name.

Description

string

An optional description for the role to explain it's purpose.

Enabled

bool

A flag to enable and disable the effect of the role.

Permissions

[RolePermissions](#rolepermissions)

The permissions assigned to the role to allow users and groups to perform certain actions.

Assignment

[RoleAssignments](#roleassignments)

The users, groups and API keys assigned to the role.

### RolePermissions

Name

Type

Description

Entries

List<[EntryPermission](#entrypermission)\>

A list of permissions for entries.

Assets

List<[EntryPermission](#entrypermission)\>

A list of permissions for assets.

### RoleAssignments

Name

Type

Description

Users

List<string>

The usernames of the users assigned to the role.

Groups

List<string>

The names of the groups assigned to the role.

ApiKeys

List<string>

The names of the API keys assigned to the role.

### EntryPermission

Name

Type

Description

Users

List<string>

The usernames of the users assigned to the role.

Groups

List<string>

The names of the groups assigned to the role.

ApiKeys

List<string>

The names of the API keys assigned to the role.

## Methods

Method

Returns

Description

[Save()](about:/help-and-docs/apis/management-dotnet/model/role-methods#save)

void

Saves changes made to the node instance.

[SaveAsync()](about:/help-and-docs/apis/management-dotnet/model/role-methods#saveasync)

Task

Saves changes made to the node instance asynchronously.

[Delete()](about:/help-and-docs/apis/management-dotnet/model/role-methods#delete)

void

Deletes the node instance.

[DeleteAsync()](about:/help-and-docs/apis/management-dotnet/model/role-methods#deleteasync)

Task

Deletes the node instance instance asynchronously.