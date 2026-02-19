1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  Content
5.  [Field](https://www.contensis.com/help-and-docs/apis/delivery-http/content/fields)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 22 July 2020

## Properties

Name

Type

Description

**type**

string

The field name given to a field type defined in the content type

**value**

any

The value of the field, which can be of any type

## Example

JSON

```
{
    "synopsis": [
        {
            "type": "mainHeading",
            "value": "Plot details"
        },
        {
            "type": "markup",
            "value": "Nearly 10 years have passed since Sarah Connor was targeted for termination by a cyborg from the future. Now her son, John, the future leader of the resistance, is the target for a newer, more deadly terminator. Once again, the resistance has managed to send a protector back to attempt to save John and his mother Sarah."
        },
        {
            "type": "memorableQuote",
            "value": {
                "text": "I'll be back!",
                "source": "Terminator T-800"
            }
        }
    ]
}
```