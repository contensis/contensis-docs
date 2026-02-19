1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Navigation

[Log in to add to favourites](/account/login)

Page last updated 24 February 2022

## Properties

Name

Type

Format

Description

**id**

string

uuid

The node identifier as a 128 bit GUID

**parentId**

string

uuid

The identifier of the parent node as a 128 bit GUID

**projectId**

string

\-

The friendly name given to the project

**displayName**

object

localized value

The localised displayName of the node

**slug**

object

localized value

The localised displayName of the node

**entryId**

string

uuid

The identifier of the referenced entry as a 128 bit GUID

**restrictedToLanguages**

string\[...\]

\-

An array of all the languages supported by the node

**childCount**

number

\-

The count of child nodes

**isCanonical**

boolean

\-

True if the node represents the canonical path for the associated entry; false otherwise

**includeInMenu**

boolean

\-

True if the node should be included in menus; false otherwise. Defaults to true. Does not stop the node from being navigable

**language**

string

language

The language that the node represents

**path**

string

URI

The path of the node

**version.versionNo**

string

\-

The version number of the node

**Entry**

object

entry

The entry associated with the node, if requested

**children**

object\[...\]

node

If a depth is specified when requesting a node then the children field would include the descendant nodes to the specified depth

**proxy**

object

\-

A proxy assigned to this node

## Example

JSON

```
{
    "id": "baf2d873-6f65-4dbe-b3ad-b4d194c963b2",
    "parentId": "28107355-a43a-4b94-bc6c-28b6ac622258",
    "projectId": "movieDatabase",
    "displayName": {
        "en-GB": "Kelly's Heroes"
    },
    "slug": {
        "en-GB": "kellys-heroes"
    },
    "entryId": "88b9941c-59bb-4954-9a8e-8c8ac3a77f45",
    "restrictedToLanguages": ["en-GB", "fr-FR"],
    "childCount": 5,
    "isCanonical": true,
    "includeInMenu": true,
    "proxy": {
        "id": "4a398293-8250-4130-a789-44b36d1c7aac",
        "parseContent": false,
        "enablePartialMatching": false
    }
}
```

JSON

```
{
    "id": "baf2d873-6f65-4dbe-b3ad-b4d194c963b2",
    "parentId": "28107355-a43a-4b94-bc6c-28b6ac622258",
    "projectId": "movieDatabase",
    "displayName": {
        "en-GB": "Kelly's Heroes"
    },
    "slug": {
        "en-GB": "kellys-heroes"
    },
    "entryId": "88b9941c-59bb-4954-9a8e-8c8ac3a77f45",
    "restrictedToLanguages": ["en-GB", "fr-FR"],
    "childCount": 5,
    "isCanonical": true,
    "includeInMenu": true,
    "proxy": {
        "id": "4a398293-8250-4130-a789-44b36d1c7aac",
        "parseContent": false,
        "enablePartialMatching": false
    }
}
```

JSON

```
{
    "id": "3B9CCCD6-D0F9-4FA7-BE8F-62A3EDCCA2DD",
    "parentId": "EFD16C0D-DE03-4D29-B979-76E20F9F1642",
    "projectId": "movieDb",
    "slug": "last-action-hero",
    "displayName": "The Last Action Hero",
    "isCanonical": true,
    "language": "en-GB",
    "path": "/en-GB/movies/action/last-action-hero",
    "childCount": 10,
    "children": [],
    "entry": {
        "sys": {
            "id": "e6976206-a488-45e3-a438-244b871f48c0"
        }
    },
    "version": {
        "versionNo": "1.0"
    },
    "includeInMenu": true
}
```