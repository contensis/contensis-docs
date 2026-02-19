A node represents a location within the navigational structure of a website. The linking of nodes as parent-child relationships forms the hierarchical structure of a website, with a node having a single parent and (optionally) multiple child nodes.

A single entry can be assigned to a node, separating the responsibility of navigation management from content editing.

Name

Type

Format

Description

id

string

[GUID](https://docs.microsoft.com/en-us/dotnet/api/system.guid)

The node identifier as a 128 bit GUID

parentId

string

[GUID](https://docs.microsoft.com/en-us/dotnet/api/system.guid)

The identifier of the parent node as a 128 bit GUID

projectId

string

The friendly name given to the project

displayName

object

[Localized value](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/localization)

The localised displayName of the node

slug

object

[Localized value](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/localization)

The localised name of the node in slug format. Automatically created from the relevant title variation if not provided. Must be in slug format if provided as a value

entryId

string

[GUID](https://docs.microsoft.com/en-us/dotnet/api/system.guid)

The identifier of the referenced entry as a 128 bit GUID

restrictedToLanguages

stringArray

An array of all the languages supported by the node

childCount

number

The count of child nodes

isCanonical

boolean

*true* if the node represents the canonical path for the associated entry; *false* otherwise

includeInMenu

boolean

*true* if the node should be included in menus; *false* otherwise. Defaults to *true*. Does not stop the node from being navigable