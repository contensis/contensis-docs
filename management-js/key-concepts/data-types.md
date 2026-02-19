## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Key concepts

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

A data type is the storage type for a field, and determines how the field data is validated and indexed for search.

Contensis supports the following basic data types:

Type

Description

Applicable Validations

string

Used for text entries such as titles, content or markup.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[maxChars](about:/help-and-docs/apis/management-js/key-concepts/validations#maxchars)  
[minChars](about:/help-and-docs/apis/management-js/key-concepts/validations#minchars)  
[regex](about:/help-and-docs/apis/management-js/key-concepts/validations#regex)  
[allowedValues](about:/help-and-docs/apis/management-js/key-concepts/validations#allowedvalues)  

integer

A whole number.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[min](about:/help-and-docs/apis/management-js/key-concepts/validations#min)  
[max](about:/help-and-docs/apis/management-js/key-concepts/validations#max)  

decimal

A number with a fractional part.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[min](about:/help-and-docs/apis/management-js/key-concepts/validations#min)  
[max](about:/help-and-docs/apis/management-js/key-concepts/validations#max)  
[decimalPlaces](about:/help-and-docs/apis/management-js/key-concepts/validations#decimalplaces)  

boolean

A value of *true* or *false*.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  

dateTime

A point in time.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[min](about:/help-and-docs/apis/management-js/key-concepts/validations#min)  
[max](about:/help-and-docs/apis/management-js/key-concepts/validations#max)  
[pastDateTime](about:/help-and-docs/apis/management-js/key-concepts/validations#pastdatetime)  

object

Any arbitrary structure as JSON or a string .

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  

stringArray

An array of strings.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[maxChars](about:/help-and-docs/apis/management-js/key-concepts/validations#maxchars)  
[minChars](about:/help-and-docs/apis/management-js/key-concepts/validations#minchars)  
[regex](about:/help-and-docs/apis/management-js/key-concepts/validations#regex)  
[allowedValues](about:/help-and-docs/apis/management-js/key-concepts/validations#allowedvalues)  
[maxCount](about:/help-and-docs/apis/management-js/key-concepts/validations#maxcount)  
[minCount](about:/help-and-docs/apis/management-js/key-concepts/validations#mincount)  

integerArray

An array of integers.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[maxCount](about:/help-and-docs/apis/management-js/key-concepts/validations#maxcount)  
[minCount](about:/help-and-docs/apis/management-js/key-concepts/validations#mincount)  

decimalArray

An array of decimals.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[min](about:/help-and-docs/apis/management-js/key-concepts/validations#min)  
[max](about:/help-and-docs/apis/management-js/key-concepts/validations#max)  
[decimalPlaces](about:/help-and-docs/apis/management-js/key-concepts/validations#decimalplaces)  
[maxCount](about:/help-and-docs/apis/management-js/key-concepts/validations#maxcount)  
[minCount](about:/help-and-docs/apis/management-js/key-concepts/validations#mincount)  

dateTimeArray

An array of dateTimes.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[min](about:/help-and-docs/apis/management-js/key-concepts/validations#min)  
[max](about:/help-and-docs/apis/management-js/key-concepts/validations#max)  
[pastDateTime](about:/help-and-docs/apis/management-js/key-concepts/validations#pastdatetime)  
[maxCount](about:/help-and-docs/apis/management-js/key-concepts/validations#maxcount)  
[minCount](about:/help-and-docs/apis/management-js/key-concepts/validations#mincount)  

objectArray

An array of objects.

[required](about:/help-and-docs/apis/management-js/key-concepts/validations#required)  
[maxCount](about:/help-and-docs/apis/management-js/key-concepts/validations#maxcount)  
[minCount](about:/help-and-docs/apis/management-js/key-concepts/validations#mincount)  

## Examples

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