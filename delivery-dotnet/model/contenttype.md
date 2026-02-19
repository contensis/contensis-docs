1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 17 October 2022

A content type resource can be retrieved from the Delivery API to understand the schema of an [Entry](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/entry "entry"). Entries are constructed and validated using the information defined in the fields collection.

Name

Type

Description

Id

string

A unique content type identifier, e.g. "actor"

ProjectId

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console

Name

[LocalizedValue](#localizedvalue)

The friendly name given to a content type

Description

[LocalizedValue](#localizedvalue)

The description text given to a content type

EntryTitleField

string

The id of the field which should be used as the title in entry listings

EntryDescriptionField

string

The id of the field which should be used as the description in entry listings

Fields

IReadOnlyList<[Field](#field)\>

A collection of fields that form the schema for an entry

Enabled

bool

A flag to indicate whether the content type is enabled and allows new entries to be created based on it

DefaultLanguage

string

The default [language code](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/key-concepts/localization) for the entries based on the content type

SupportedLanguages

IReadOnlyList<string>

 

WorkflowId

string

The workflow that derived entries will

DataFormat

string

Either 'entry' or 'asset'

PreviewUrl

string

The URL where an example of an entry based on the content type can be viewed

Version

[VersionInfo](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/model/versioninfo)

Version information about the content type

IncludeInDelivery

bool

If set to 'false', no entries for the content type will be returned in delivery and will instead result in a HTTP status of 403 Forbidden. Any entry that is included in delivery that has a link to an item that is not included in delivery will still have the link returned, however no further data will be returned if the entry is retrieved with a link depth.

## Field

The field object is the definition of a field within an entry. The field also contains the validations and editor configuration that is used within the Contensis UI and services.

Name

Type

Description

Id

string

A unique field identifier

Name

[LocalizedValue](#localizedvalue)

A friendly name for the field

Description

[LocalizedValue](#localizedvalue)

The description for the field's purpose

DataType

[DataType](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/key-concepts/data-types)

The field data type

DataFormat

string

The field [DataFormat](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/key-concepts/data-format)

Default

[LocalizedValue](#localizedvalue)

The default value for the field if no value is provided by an editor

## LocalizedValue

A localized value is an object that has values that are keyed by [language codes](https://www.contensis.com/help-and-docs/apis/delivery-dotnet/key-concepts/localization) which allows multilingual variations of a specific property.