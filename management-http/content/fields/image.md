1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  [Fields](/help-and-docs/apis/management-http/content/fields)

[Log in to add to favourites](/account/login)

Page last updated 13 May 2022

## Properties

Name

Type

Format

Description

**asset**

object

asset

The asset that is linked to from the entry

**altText**

string

\-

The image alt text, defined in the entry

**caption**

string

\-

The image caption, defined in the entry

**transformations**

object

image transformation

The transformations that will be applied to the image

## Example

JSON

```
{
    "asset": {
        "sys": {
            "id": "a83c9fcc-51ef-41aa-878f-af5a33ba4b2f",
            "dataFormat": "asset",
            "contentTypeId": "image",
            "language": "en-GB"
        }
    },
    "caption": "Fight club is a great film!",
    "altText": "The 1999 Fight Club image poster",
    "transformations": {  
        "size": {  
            "height": 100,
            "width": 100
        },
        "flip": "h",
        "rotate": 95,
        "crop": {  
            "width": 100,
            "height": 100,
            "x": 10,
            "y": 20
        },
        "quality": 95
    }
}
```

JSON

```
{
    "asset": {
        "sys": {
            "id": "a83c9fcc-51ef-41aa-878f-af5a33ba4b2f",
            "dataFormat": "asset",
            "contentTypeId": "image",
            "language": "en-GB"
        }
    },
    "caption": "Fight club is a great film!",
    "altText": "The 1999 Fight Club image poster",
    "transformations": {  
        "size": {  
            "height": 100,
            "width": 100
        },
        "flip": "h",
        "rotate": 95,
        "crop": {  
            "width": 100,
            "height": 100,
            "x": 10,
            "y": 20
        },
        "quality": 95
    }
}
```

JSON

```
{
    "asset": {
        "sys": {
            "id": "a83c9fcc-51ef-41aa-878f-af5a33ba4b2f",
            "dataFormat": "asset",
            "language": "en-GB"
        }
    },
    "caption": "Fight club is a great film!",
    "altText": "The 1999 Fight Club image poster",
    "transformations": {  
        "size": {  
            "height": 100,
            "width": 100
        },
        "flip": "h",
        "rotate": 95,
        "crop": {  
            "width": 100,
            "height": 100,
            "x": 10,
            "y": 20
        },
        "quality": 95
    }
}
```