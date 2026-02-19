## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 10 December 2024

## On this page

-   [Properties](#properties)
-   [Field](#field)
-   [Properties](#properties-1)
-   [Localized value](#localized-value)
-   [Example](#example)

A content type resource can be retrieved from the Delivery API to understand the schema of an [entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry). Entries are constructed and validated using the information defined in the fields collection.

## Properties

Name

Type

Format

Description

id

string

A unique content type identifier

projectId

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console

name

object

[Localized value](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

The friendly name given to a content type

description

object

[Localized value](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

The description text given to a content type

entryTitleField

string

The id of the field which should be used as the title in entry listings

fields

object \[…\]

[Field](#field)

A collection of fields that form the schema for an entry

enabled

boolean

defaultLanguage

string

[Language code](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

supportedLanguages

string \[…\]

[Language code](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

workflowId

string

The workflow that derived entries will

dataFormat

string

Either *entry* or *asset*

previewUrl

string

The URL where an example of an entry based on the content type can be viewed

version

object

[Version](https://www.contensis.com/help-and-docs/apis/delivery-js/model/version)

Version information about the content type

includeInDelivery

boolean

If set to 'false', no entries for the content type will be returned in delivery and will instead result in a HTTP status of 403 Forbidden. Any entry that is included in delivery that has a link to an item that is not included in delivery will still have the link returned, however no further data will be returned if the entry is retrieved with a link depth.

## Field

The field object is the definition of a field within an entry. The field also contains the validations and editor configuration that is used within the Contensis UI and services.

### Properties

Name

Type

Format

Description

id

string

A unique field identifier

name

object

[Localized value](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

A friendly name for the field

description

object

[Localized value](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

The description for the field's purpose

dataType

string

[Data type](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/data-types)

The field data type

dataFormat

string

[Data type](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/data-formats)

The field data format

default

object

[Localized value](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization)

The default value for the field if no value is provided by an editor

validations

object

The validations that will be performed on the field when the entry is either created or updated

editor

object

Editor

Configuration for the Contensis entry editor

## Localized value

A localized value is an object that has values that are keyed by [language codes](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/localization) which allows multilingual variations of a specific property.

## Example

TypeScript

```
// Using TypeScript, or ES Module await syntax
const contentType = await client.contentTypes.get('<content-type-id>');

console.log(contentType.name['en-GB']);
```

JavaScript

```
// Using Common JS promise callback syntax
client.contentTypes.get('<content-type-id>')
  .then(function (contentType) {
    console.log(contentType.name['en-GB']);
  });
```

## On this page

-   [Properties](#properties)
-   [Field](#field)
-   [Properties](#properties-1)
-   [Localized value](#localized-value)
-   [Example](#example)