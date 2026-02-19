1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Entries

[Log in to add to favourites](/account/login)

Page last updated 06 November 2024

Call the entries.resolve() method in our delivery client to get an entry or a list of entries with all content fields resolved

## Call signatures

TypeScript

```
resolve(entry: Entry, fields?: string[]): Promise<Entry>;

resolve(entryArray: Entry[], fields?: string[]): Promise<Entry[]>;

resolve(pagedListOfEntries: PagedList<Entry>, fields?: string[]): Promise<PagedList<Entry>>;
```

## Parameters

Name

Type

Description

entry

[Entry](/help-and-docs/apis/delivery-js/model/entry)

An entry object containing the sys.id of the entry to resolve

entryArray

[Entry](/help-and-docs/apis/delivery-js/model/entry) \[...\]

An array of entry objects as above

pagedListOfEntries

[PagedList](/help-and-docs/apis/delivery-js/model/paged-list)<[Entry](/help-and-docs/apis/delivery-js/model/entry)\>

A paged list containing entry objects as above

fields

string \[...\]

The ids of the fields inside the entry containing linked content to resolve

## Returns

A Promise that will resolve with an [Entry](/help-and-docs/apis/delivery-js/model/entry), an [Entry](/help-and-docs/apis/delivery-js/model/entry) array, or a [Paged List](/help-and-docs/apis/delivery-js/model/paged-list) of [Entry](/help-and-docs/apis/delivery-js/model/entry)

## Example

JavaScript

```
client.entries
  .get('<entry_id>')
  .then(function (entry) {
    // This is pointless as we will be resolving the entry we
    // have just returned with the call to .get()
    console.log(client.entries.resolve(entry, ["actor", "studio"]));
  });

client.entries
  .list('<content_type_id>')
  .then(function (entryList) {
    entryList.items.forEach(item => (
      //
      console.log(client.entries.resolve(item))
    ))
  });
```