1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Entries

[Log in to add to favourites](/account/login)

Page last updated 13 November 2024

## On this page

-   [Unresolved entries](#unresolved-entries)
-   [Resolved entries](#resolved-entries)
-   [Example](#example)

An entry can link to other entries or assets as [entry](/help-and-docs/apis/delivery-js/model/entry), [asset](/help-and-docs/apis/delivery-js/model/asset) or [image](/help-and-docs/apis/delivery-js/model/image) field types. They can be defined as a standard entry field or as a [composed](/help-and-docs/apis/delivery-js/model/composed) field type in the content type. These links can be singular or multiples of the same content type for example a field containing a link (or multiple links) to an Actor content type entry, or an Image.

Linked content can be [unresolved](#unresolved-entries) or [resolved](#resolved-entries) depending on whether a value for linkDepth has been provided when retrieving entries using the [get](/help-and-docs/apis/delivery-js/entries/get-entry), [list](/help-and-docs/apis/delivery-js/entries/list-entries) or [search](/help-and-docs/apis/delivery-js/entries/search/search-basics) entry methods. This is also supported when retrieving nodes but is referenced as entryLinkDepth.

## Unresolved entries

An unresolved entry or asset is essentially a subset of the entry structure with enough information to get the correct entry language variation. A subsequent service call is required to obtain the linked content by passing the returned field value to the resolve method. Entries containing links to other entries and assets are returned unresolved by default.

## Resolved entries

Entries can be resolved automatically in the service to a maximum depth of 10 using the linkDepth parameter in any retrieval operation. Resolving entries in a single call can significantly improve the render performance of your webpage or application. Whilst fewer network requests can be beneficial, it can also be detrimental if the linkDepth is too deep, or if there are many linked fields.

Return an entry by its ID with all linked content fields resolved to a depth of 1

TypeScript

```
const linkDepth = 1;
const entry = await client.entries.get("<entry-id>", linkDepth);
    // many methods can take a linkDepth argument    ^^^^^^^^^
```

### Field-specific link depths:

From version 16 of Contensis onwards, if you want to specify link depths for individual fields, you can specify the fieldLinkDepths parameter on all Delivery API methods that retrieve entries. This is a simple object containing field paths and link depth values. Matching field paths override the link depth and where more than one field path matches a field, the most specific (longest) is used. The example below will resolve to a link depth of 1 for all fields, except for the composer field which is resolved to a link depth of 2, though the entryLink field in a linkedEntryComponent in that composer is overridden to return to a link depth of 1.

Get a list of entries using search with all fields resolved to a depth of 1 and composer fields resolved to a depth of 2, while limiting the entry link field inside a component composer item to resolve links to a depth of just 1

TypeScript

```
const query = new Query(
  Op.contains('title', 'batman'),
  Op.greaterThan('runtime', 200)
);

query.fieldLinkDepths = {
  composer: 2,
  'composer.linkedEntryComponent.entryLink': 1
};

const pagedResult = await client.entries.search(query, 1);

console.log(pagedResult.totalCount);
console.log(pagedResult.items);
```

### Resolution rules

When a linked entry is accessed then the following rules apply:

-   If a language **has** been specified in the link, then the specific language variation will be returned.
-   If a language **has** been specified in the link, but the specific language variation does not exist, then null will be returned or will not be included in the array.
-   If a language **has not** been specified, then the *defaultLanguage* value defined in the [content type](/help-and-docs/apis/delivery-js/model/content-type) will be used to select the appropriate entry variation to return.
-   If a language **has not** been specified and there is no default variation, then null will be returned.

## Example

TypeScript

```
resolve(entry: Entry, fields?: string[]): Promise<Entry>;

resolve(entryArray: Entry[], fields?: string[]): Promise<Entry[]>;

resolve(pagedListOfEntries: PagedList<Entry>, fields?: string[]): Promise<PagedList<Entry>>;
```

TypeScript

```
const entry = await client.entries.get('<entry-id>');
console.log(client.entries.resolve(entry));

const entryList = await client.entries.list('<content-type-id>');
for (const item of entryList.items) {
  console.log(client.entries.resolve(item));
}
```

## On this page

-   [Unresolved entries](#unresolved-entries)
-   [Resolved entries](#resolved-entries)
-   [Example](#example)