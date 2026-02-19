A full [overview of entries can be found here](https://www.contensis.com/help-and-docs/guides/authoring-and-managing-content/entries/overview "Entries").

An entry definition in the Delivery API contains a mixture of standard properties and properties that have been defined by the content type that an entry is based on.

These are the standard properties that all entries have. An entry can have multiple language variations, which can be be edited, versioned and published independently. In the Delivery API context only a single language variation is available for an entry at any one time.

Name

Type

Description

Id

Guid

The entry identifier.

ContentTypeId

string

The API identifier of the content type that the entry is based on.

ProjectId

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

DataFormat

string

Either 'entry' or 'asset'.

Language

string

The language of the entry instance.

AvailableLanguages

IReadonlyCollection<string>

A list of available languages for the entry.

Version

[VersionInfo](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/versioninfo)

Version information for the entry.

Metadata

Metadata

Metadata associated with the entry instance.

Owner

string

The id of the entry owner.

Slug

string

The entry slug token.

Uri

string

The canonical location of the entry.

AllUris

IReadonlyCollection<string>

All the locations for the entry, including the canonical URI.

Workflow

[EntryWorkflow](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry-workflow)

The current workflow details for the entry.

IsPublished

boolean

Returns whether the entry is published.

Method

Returns

Description

[Get(string fieldName, bool autoResolve)](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry-methods "Entry methods")

dynamic

Gets a field item by name and returns a dynamic object.

[Get<Type>(string fieldName, bool autoResolve)](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry-methods "Entry methods")

<Type>

Gets a field item by name and attempts to cast to the specified generic type.

[HasValue(string fieldName)](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry-methods "Entry methods")

bool

A helper function to determine whether a field exists and has a value.