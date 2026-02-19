1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Key Concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 24 September 2024

A data type is the storage type for a field, and determines how the field data is validated and indexed for search.

Contensis supports the following basic data types:

Type

Description

Applicable Validations

string

Used for text entries such as titles, content or markup.

required  
maxChars  
minChars  
regex  
allowedValues

integer

A whole number.

required  
min  
max

decimal

A number with a fractional part.

required  
min  
max  
decimalPlaces

boolean

A value of *true* or *false*.

required

dateTime

A point in time.

required  
min  
max  
pastDateTime

object

Any arbitrary structure as JSON or a string.

required

stringArray

An array of strings.

required  
maxChars  
minChars  
regex  
allowedValues  
maxCount  
minCount

integerArray

An array of integers.

required  
maxCount  
minCount

decimalArray

An array of decimals.

required  
min  
max  
decimalPlaces  
maxCount  
minCount

dateTimeArray

An array of dateTimes.

required  
min  
max  
pastDateTime  
maxCount  
minCount

objectArray

An array of objects.

required  
maxCount  
minCount

**Example**

JSON

```
{
    "string": "This is a simple string",
    "integer": 24,
    "decimal": 1.34,
    "boolean": true,
    "dateTime": "2016-10-12T09:29:18.5144641+01:00",
    "object": {
        "id": "12345",
        "name": "item1"
    },
    "stringArray": [
        "Item 1",
        "Item 2",
        "Item 3"
    ],
    "integerArray": [
        1,2,3
    ],
    "decimalArray": [
        1.2, 3.4, 5.6
    ],
    "dateTimeArray": [
        "2017-03-07T14:37:27.0998174+00:00",
        "2017-03-07T14:39:16.3337294+00:00",
        "2017-03-07T14:39:19.3495296+00:00"
    ],
    "objectArray": [
        {
            "id": "12345",
            "name": "item1"
        },
        {
            "id": "67890",
            "name": "item2"
        }
    ]
}
```