## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Entries

[Log in to add to favourites](/account/login)

Page last updated 13 November 2024

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Example](#example)
-   [Using options](#example-using-options)

Call the entries.get() method in our delivery client to get a single entry

## Call signatures

TypeScript

```
get(id: string): Promise<Entry>

get(options: EntryGetOptions): Promise<Entry>
```

## Parameters

Name

Type

Description

id

string

The id of the entry

options

[EntryGetOptions](/help-and-docs/apis/delivery-js/model/entry-get-options)

An object specifying the id, language, fields to return and linkDepth.

## Returns

A Promise that will resolve with the [Entry](/help-and-docs/apis/delivery-js/model/entry)

## Example

TypeScript

```
// Using TypeScript, or ES Module await syntax
const entry = await client.entries.get('<entry_id>');

console.log(entry.entryTitle);
```

JavaScript

```
// Using Common JS promise callback syntax
client.entries.get('<entry_id>')
  .then(function (entry) {
    console.log(entry.title);
  });
```

#### Using options

Get only the title and overview fields of the French entry variation resolving linked content to a depth of 2

TypeScript

```
// Using TypeScript, or ES Module await syntax
const entry = await client.entries.get({
  id: '<entry_id>',
  language: 'fr-FR',
  linkDepth: 2,
  fields: ['title', 'overview']
});

console.log(entry.title);
console.log(entry.overview);
```

Get only the title and overview fields of the French entry variation resolving linked content to a depth of 2

JavaScript

```
// Using Common JS promise callback syntax
client.entries
  .get({
    id: '<entry_id>',
    language: 'fr-FR',
    linkDepth: 2,
    fields: ['title', 'overview']
  })
  .then(function (entry) {
    console.log(entry.title);
    console.log(entry.overview);
  });
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Example](#example)
-   [Using options](#example-using-options)