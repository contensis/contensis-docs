[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 20 July 2021

The data format property is used as an extension of a [data type](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/data-types "Link to Data types") to describe the structure and intent of the data. For example, a *location* has a data type of *object*, and a data format of *location*. Another example is a HTML block, which has a data type of *string* and a data format of *html*.

The data format is a string value and is designed to allow custom types to be added.

## Supported data formats

The following list contains the data formats that are currently understood by Contensis:

Data format

Data type

Description

Applicable Validations

[entry](https://www.contensis.com/help-and-docs/apis/management-http/content/entries "Link to Entry")

object

An entry format for storing content.

required  
allowedContentTypes

asset

object

An asset format that represents a file resource.

required  
allowedContentTypes

[location](https://www.contensis.com/help-and-docs/apis/management-http/content/fields/location "Link to Location")

object

Represents a point on the surface of the Earth.

required

[quote](https://www.contensis.com/help-and-docs/apis/management-http/content/fields/quote "Link to Quote")

object

A quote with text and a source.

required  
requiredFields

[dateRange](https://www.contensis.com/help-and-docs/apis/management-http/content/fields/date-range "Link to Date range")

object

Represents a range of date times.

required  
min  
max  
pastDateTime

[image](https://www.contensis.com/help-and-docs/apis/management-http/content/fields/image "Link to Image")

object

Wraps an Asset with an additional caption property.

required  
requiredFields

field

objectArray

Represents a [composed](https://www.contensis.com/help-and-docs/apis/management-http/content/fields/composed-field "Link to Composed") type, defined as an objectArray data type.

required  
allowedFieldTypes

component.\*

object

Represents a [component](https://www.contensis.com/help-and-docs/apis/management-http/content/components "Link to Component") type. The asterisk represents the component id.

required  
allowedFieldTypes

heading

string

Represents a document heading.

required

html

string

A string of HTML markup.

required

markdown

string

A string of markdown markup.

required