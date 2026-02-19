## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Entries

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## On this page

-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Example](#example---using-content-type-id)
-   [Example - using entry list options](#example---using-entry-list-options)

Call the entries.list() method in our delivery client to get a paged list of entries of a given content type

### Call signatures

TypeScript

```
list(contentTypeId: string): Promise<PagedList<Entry>>

list(options: EntryListOptions): Promise<PagedList<Entry>>
```

### Parameters

Name

Type

Description

contentTypeId

string

The id of the content type

options

[EntryListOptions](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry-list-options)

An object specifying the content type id, language, page options, ordering, fields to return and linkDepth.

### Returns

A Promise that will resolve with a [Paged List](https://www.contensis.com/help-and-docs/apis/delivery-js/model/paged-list) of [Entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

### Example

Get a list of entries of a given content type API ID

TypeScript

```
// Using TypeScript, or ES Module await syntax
const entryList = await client.entries.list('<content-type-id>');

for (const entry of entryList.items) {
  console.log(entry.entryTitle);
}
```

Get a list of entries of a given content type API ID

JavaScript

```
// Using Common JS promise callback syntax
client.entries.list('<content-type-id>')
  .then(function (entryList) {
    entryList.items.forEach(item => (
      console.log(item.entryTitle)
    ))
  });
```

### Example - using entry list options

Get only the title and overview fields of the French entry variations resolving linked content to a depth of 2

TypeScript

```
// Using TypeScript, or ES Module await syntax
const entryList = await client.entries.list({
  id: '<content-type-id>',
  language: 'fr-FR',
  linkDepth: 2,
  fields: ['title', 'overview']
})

for (const entry of entryList.items) {
  console.log(entry.title);
  console.log(entry.overview);
}
```

Get only the title and overview fields of the French entry variations resolving linked content to a depth of 2

JavaScript

```
// Using Common JS promise callback syntax
client.entries
  .list({
    id: '<content-type-id>',
    language: 'fr-FR',
    linkDepth: 2,
    fields: ['title', 'overview']
  })
  .then(function (entryList) {
    entryList.items.forEach(item => (
      console.log(item.title);
      console.log(item.overview);
    ))
  });
```

## On this page

-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Example](#example---using-content-type-id)
-   [Example - using entry list options](#example---using-entry-list-options)