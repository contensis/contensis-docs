## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Delivery API](/help-and-docs/apis/delivery-http)
4.  key-concepts

[Log in to add to favourites](/account/login)

Page last updated 19 September 2024

The data format property is used as an extension of a [data type](/help-and-docs/apis/delivery-http/key-concepts/data-types) to describe the structure and intent of the data. For example, a *location* has a data type of *object*, and a data format of *location*. Another example is a HTML block, which has a data type of *string* and a data format of *html*.

The data format is a string value and is designed to allow custom types to be added.

## Supported data formats

The following list contains the data formats that are currently understood by Contensis:

Data format

Data type

Description

[entry](/help-and-docs/apis/delivery-http/content/entry)

object

An entry format for storing content.

[asset](/help-and-docs/apis/delivery-http/content/fields/asset)

object

An asset format that represents a file resource.

[location](/help-and-docs/apis/delivery-http/content/fields/location)

object

Represents a point on the surface of the Earth.

[quote](/help-and-docs/apis/delivery-http/content/fields/quote)

object

A quote with text and a source.

[dateRange](/help-and-docs/apis/delivery-http/content/fields/date-range)

object

Represents a start and end point in time.

[image](/help-and-docs/apis/delivery-http/content/fields/image)

object

Wraps an Asset with an additional caption property.

field

objectArray

Represents a [composed](/help-and-docs/apis/delivery-http/content/fields/composed-field) type, defined as an objectArray data type.

heading

string

Represents a document heading.

html

string

A string of HTML markup.

markdown

string

A string of markdown markup.