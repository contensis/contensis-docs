An entry definition in the Management API contains a mixture of standard properties and properties that have been defined by the content type that an [entry](https://www.contensis.com/help-and-docs/user-guides/authoring/entries "Entries") is based on.

These are the standard properties that all entries have. An entry can have multiple language variations, which can be be edited, versioned and published independently. A single language variation is available for an entry at any one time.

Name

Type

Description

Id

int

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

A list of languages which have available translations.

UnavailableLanguages

IReadonlyCollection<string>

A list of languages which the entry can be translated to but have yet to be completed.

Version

[VersionInfo](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/versioninfo ".NET Management API – VersionInfo ")

Version information for the entry.

IsPublished

bool

Returns whether the entry is published.

Metadata

Metadata

Metadata associated with the entry instance.

Owner

string

The id of the entry owner.

Workflow

[Workflow](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/workflow ".NET Management API – Workflow")

The current workflow details for the entry.

TranslationState

TranslationState enum

The translation status of the entry. Possible values are *None, NeverTranslated, Translated, TranslationOutOfDate, NoDefaultLanguage, AvailableForTranslation, NotAvailableForTranslation.*

Slug

string

The entry slug token.

Method

Returns

Description

[Get(string fieldName)](about:/help-and-docs/apis/management-dotnet/model/entry-methods#get "NET Management API Entry methods – Get")

dynamic

Gets a field item by name and returns a dynamic object.

[Get<Type>(string fieldName)](about:/help-and-docs/apis/management-dotnet/model/entry-methods#get-t "NET Management API Entry methods – Get <T>")

<Type>

Gets a field item by name and attempts to cast to the specified generic type.

[HasValue(string fieldName)](about:/help-and-docs/apis/management-dotnet/model/entry-methods#hasvalue "NET Management API Entry methods – HasValue")

bool

A helper function to determine whether a field exists and has a value.

[Save()](about:/help-and-docs/apis/management-dotnet/model/entry-methods#save "NET Management API Entry methods – Save")

void

Saves changes made to the entry instance.

[SaveAsync()](about:/help-and-docs/apis/management-dotnet/model/entry-methods#saveasync "NET Management API Entry methods – SaveAsync")

Task

Saves changes made to the entry instance asynchronously.

[Delete(bool permanent)](about:/help-and-docs/apis/management-dotnet/model/entry-methods#delete "NET Management API Entry methods – Delete")

void

Deletes entry variation instance.

[DeleteAsync(bool permanent)](about:/help-and-docs/apis/management-dotnet/model/entry-methods#deleteasync "NET Management API Entry methods – DeleteAsync")

Task

Deletes entry variation instance asynchronously.