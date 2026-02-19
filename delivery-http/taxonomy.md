## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Delivery API](/help-and-docs/apis/delivery-http)

[Log in to add to favourites](/account/login)

Page last updated 09 July 2020

## Properties

Name

Type

Description

Example

**key**

string

The taxonomy key

0/1

**name**

string

The localized taxonomy name

**path**

string

The full taxonomy node path

Root/Movies/Genres

**hasChildren**

boolean

Whether or not the node has any child nodes

**children**

object\[...\]

A list of child taxonomy nodes

## Example

This example shows a taxonomy node object with child taxonomy nodes

JSON

```
{
    "key": "0",
    "name": "Root",
    "path": "Root",
    "hasChildren": true,
    "children": [
        {
            "key": "0/1",
            "name": "Movies",
            "path": "Root/Movies",
            "hasChildren": true,
            "children": [
                {
                    "key": "0/1/2",
                    "name": "Genres",
                    "path": "Root/Movies/Genres",
                    "hasChildren": false,
                    "children": []
                }
            ]
        }        
    ]
}
```

This example shows a taxonomy node object with child taxonomy nodes

JSON

```
{
    "key": "0",
    "name": "Root",
    "path": "Root",
    "hasChildren": true,
    "children": [
        {
            "key": "0/1",
            "name": "Movies",
            "path": "Root/Movies",
            "hasChildren": true,
            "children": [
                {
                    "key": "0/1/2",
                    "name": "Genres",
                    "path": "Root/Movies/Genres",
                    "hasChildren": false,
                    "children": []
                }
            ]
        }        
    ]
}
```