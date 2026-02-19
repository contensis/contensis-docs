The data format property is used as an extension of a [data type](https://www.contensis.com/help-and-docs/apis/delivery-js/key-concepts/data-types) to describe the structure and intent of the data. For example, a *location* has a data type of *object*, and a data format of *location*. Another example is a HTML block, which has a data type of *string* and a data format of *html*.

The data format is a string value and is designed to allow custom types to be added.

The following list contains the data formats that are currently understood by Contensis:

Data format

Data type

Description

[entry](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry)

object

An entry format for storing content.

[asset](https://www.contensis.com/help-and-docs/apis/delivery-js/model/asset)

object

An asset format that represents a file resource.

[location](https://www.contensis.com/help-and-docs/apis/delivery-js/model/location)

object

Represents a point on the surface of the Earth.

[quote](https://www.contensis.com/help-and-docs/apis/delivery-js/model/quote)

object

A quote with text and a source.

[dateRange](https://www.contensis.com/help-and-docs/apis/delivery-js/model/date-range)

object

Represents a start and end point in time.

[image](https://www.contensis.com/help-and-docs/apis/delivery-js/model/image)

object

Wraps an asset with an additional caption property.

field

objectArray

Represents a [composed](https://www.contensis.com/help-and-docs/apis/delivery-js/model/composed) type, defined as an objectArray data type.

heading

string

Represents a document heading.

html

string

A string of HTML markup.

markdown

string

A string of markdown markup.