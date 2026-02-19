## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

## On this page

-   [Data properties](#data-properties)
-   [Standard properties](#standard-properties)
-   [Entry](#entry)
-   [Sys](#sys)
-   [Example](#example)

An entry definition in the Delivery API contains a mixture of standard properties and properties that have been defined by the content type that an entry is based on.

## Data properties

Data properties are items defined by the [fields collection](https://www.contensis.com/help-and-docs/apis/delivery-js/model/content-type#field) set in a content type.

## Standard properties

These are the standard properties that all entries have. The language property is the indexer for the entry data as an entry can have multiple language variations which can be be edited and versioned independently. In the Delivery API context only a single language variation is available on an entry.

### Entry

Name

Type

Format

Description

\[field id\]

Any

Any

Field data that is defined in the associated [content type](https://www.contensis.com/help-and-docs/apis/delivery-js/model/content-type#field). The data is keyed by a unique field id.

sys

object

[Sys](#sys)

The container of the entry system data.

### Sys

Name

Type

Format

Description

id

string

GUID

The entry identifier as a 128 bit GUID.

projectId

string

\[optional\] The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

contentTypeId

string

The API identifier of the content type that the entry is based on.

dataFormat

string

Either *entry* or *asset.*

language

string

[Language code](/help-and-docs/apis/delivery-js/key-concepts/localization)

The language code of the entry variation.

availableLanguages

string\[\]

[Language code](/help-and-docs/apis/delivery-js/key-concepts/localization)

\[optional\] A list languages which have available translations.

uri

string

URI

The entry uri.

allUris

string\[\]

URI

All uris associated with the entry.

metadata

object

\[optional\] Metadata associated with the entry instance.

workflow

object

\[optional\] Workflow associated with the entry instance.

workflow.id

string

The API identifier of the workflow that the entry is using.

workflow.state

string

The API identifier of the current workflow state of the entry.

isPublished

boolean

\[optional\] If the entry is currently published then the value will be *true*. If the entry has yet to be published or has been unpublished it will be *false*.

version

object

[Version](/help-and-docs/apis/delivery-js/model/version)

\[optional\] Version info specific to the entry variation.

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

## On this page

-   [Data properties](#data-properties)
-   [Standard properties](#standard-properties)
-   [Entry](#entry)
-   [Sys](#sys)
-   [Example](#example)