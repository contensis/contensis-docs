The DataFormat property is used as an extension of a [DataType](/help-and-docs/apis/management-dotnet/key-concepts/data-types) to describe or identify the structure and intent of the data. For example, a [Location](/help-and-docs/apis/management-dotnet/model/location) has a DataType of *object*, and a DataFormat of *location*. Another example is a HTML block, which has a DataType of *string* and a DataFormat of *html*.

The DataFormat is a string value and is designed to allow custom types to be added.

The following list contains the data formats that are understood by Contensis.

DataFormat

DataType

Description

[entry](/help-and-docs/apis/management-dotnet/model/entry)

object

An entry format for storing content.

asset

object

An asset format that represents a file resource.

[location](/help-and-docs/apis/management-dotnet/model/location)

object

Represents a point on the surface of the Earth.

[quote](/help-and-docs/apis/management-dotnet/model/quote)

object

A quote with text and a source.

[dateRange](/help-and-docs/apis/management-dotnet/model/daterange)

object

Represents a start and end point in time.

[image](/help-and-docs/apis/management-dotnet/model/image)

object

Wraps an asset with an additional caption property.

[component](/help-and-docs/apis/management-dotnet/key-concepts/components).\*

object

Represents a component type. The format is the component id with a 'component.' prefix.

field

objectArray

Represents a [ComposedField](/help-and-docs/apis/management-dotnet/model/composedfield) type, defined as an `objectArray` DataType.

heading

string

Represents a document heading.

html

string

A string of HTML markup.

markdown

string

A string of Markdown markup.

taxonomy

string

A taxonomy key.