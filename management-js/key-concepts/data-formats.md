The data format property is used as an extension of a [data type](/help-and-docs/apis/management-js/key-concepts/data-types) to describe the structure and intent of the data. For example, a *location* has a data type of *object*, and a data format of *location*. Another example is a HTML block, which has a data type of *string* and a data format of *html*.

The data format is a string value and is designed to allow custom types to be added.

The following list contains the data formats that are currently understood by Contensis:

Data format

Data type

Description

Applicable Validations

[entry](/help-and-docs/apis/management-js/model/entry)

object

An entry format for storing content.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[allowedContentTypes](about:/help-and-docs/apis/management-js/key-concepts/validations#allowedcontenttypes)

asset

object

An asset format that represents a file resource.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[allowedContentTypes](about:/help-and-docs/apis/management-js/key-concepts/validations#allowedcontenttypes)

[location](/help-and-docs/apis/management-js/model/location)

object

Represents a point on the surface of the Earth.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)

[quote](/help-and-docs/apis/management-js/model/quote)

object

A quote with text and a source.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[requiredFields](about:/help-and-docs/apis/management-js/key-concepts/validations#requiredfields)

[dateRange](/help-and-docs/apis/management-js/model/date-range)

object

Represents a range of date times.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[min](about:/help-and-docs/apis/management-js/key-concepts/validations#min)  
[max](about:/help-and-docs/apis/management-js/key-concepts/validations#max)  
[pastDateTime](about:/help-and-docs/apis/management-js/key-concepts/validations#pastdatetime)

[image](/help-and-docs/apis/management-js/model/image)

object

Wraps an Asset with an additional caption property.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[requiredFields](about:/help-and-docs/apis/management-js/key-concepts/validations#requiredfields)

field

objectArray

Represents a [composed](/help-and-docs/apis/management-js/model/composed) type, defined as an objectArray data type.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[allowedFieldTypes](about:/help-and-docs/apis/management-js/key-concepts/validations#allowedfieldtypes)

component.\*

object

Represents a [component](/help-and-docs/guides/modelling-content/components/overview) type. The asterisk represents the component id.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[allowedFieldTypes](about:/help-and-docs/apis/management-js/key-concepts/validations#allowedfieldtypes)

heading

string

Represents a document heading.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)

html

string

A string of HTML markup.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)

markdown

string

A string of markdown markup.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)