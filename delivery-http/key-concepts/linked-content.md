1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  key-concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

An entry can link to other entries or assets as [entry](https://www.contensis.com/help-and-docs/apis/delivery-http/content/entry), [asset](https://www.contensis.com/help-and-docs/apis/delivery-http/content/fields/asset) or [image](https://www.contensis.com/help-and-docs/apis/delivery-http/content/fields/image) field types. They can be defined as standard entry fields or as a [composed](https://www.contensis.com/help-and-docs/apis/delivery-http/content/fields/composed-field) field type in the content type. These link objects can be singular or arrays of links of the same content type e.g. Actors.

Linked content can be unresolved or resolved depending on whether a linkDepth or fieldLinkDepths value has been provided.

## Unresolved entries

An unresolved entry or asset is essentially a subset of the entry structure with enough information to get the correct entry language variation. A subsequent HTTP call is required to obtain the linked content. Unresolved entries and assets is the default behaviour for linked content.

## Properties

Name

Type

Format

Description

id

string

GUID

The entry identifier as a 128 bit GUID

dataFormat

string

Either *entry* or *asset*

language

string

[Language code](https://www.contensis.com/help-and-docs/apis/delivery-http/key-concepts/localization)

\[Optional\] The language code of the linked entry variation

### Example

This example shows an unresolved entry.

JSON

```
{
    "id": "0a48e187-43e0-4df0-ae62-8eba4d478036",
    "dataFormat": "entry",
    "language": "en-GB"
}
```

## Resolved entries

Entries can be resolved automatically to a maximum depth of 10 using the linkDepth or fieldLinkDepths parameter in any retrieval operation. Being able to resolve entries in a single HTTP call can significantly improve the render performance of your webpage or application. Whilst fewer network requests can be beneficial, it can also be detrimental if the linkDepth in particular is too deep or where there are many link fields. In such cases, it is more efficient to specify individual fieldLinkDepths.

### Field-specific link depths:

From version 16 of Contensis onwards, if you want to specify link depths for individual fields, you can use the fieldLinkDepths querystring parameter on all Delivery API search endpoints. This is a simple 'dictionary' of field paths and link depth values. Matching field paths override the link depth and where more than one field path matches a field, the most specific (longest) is used. This example will resolve to a link depth of 1 for all fields, except for the composer field which is resolved to a link depth of 2, though the entryLink field in a linkedEntryComponent in that composer is overridden to return to a link depth of 1.

HTTP

```
GET: /api/delivery/projects/{projectId}/entries/search?where=[{"field":"title","contains":"Batman"},{"field":"runtime","greaterThan":200}]&linkDepth=1&fieldLinkDepths={"composer":2, "composer.linkedEntryComponent.entryLink":1}
```

### Resolution rules

When a linkDepth or fieldLinkDepths are provided to an entry retrieval operation, then the following rules apply:

-   If a language **is** specified, then the specific language variation will be returned
-   If a language **is** specified but the specific language variation does not exist, then null will be returned or will not be included in the array
-   If a language **is not** specified, then the *defaultLanguage* value defined in the [content type](https://developer.zengenti.com/contensis/api/delivery/http/model/content-type.html) will be used to select the appropriate entry variation to return.
-   If a language **is not** specified and there is no default variation, then null is returned.