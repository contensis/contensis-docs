1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Fields](https://www.contensis.com/help-and-docs/apis/management-http/content/fields)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 May 2022

## Properties

Name

Type

Description

**size**

object

The image height and width resize transformations

**flip**

string

The orientation flip name to apply

**rotate**

integer

The image rotation in degrees

**crop**

object

The image crop details specifying width and height, and x and y coordinates

**quality**

integer

The quality in percentage

## Example

JSON

```
{
  "poster": {
    "asset": {
      "sys": {
        "id": "fab3fdc6-89fd-4efa-bfe0-30722fb87661",
        "dataFormat": "asset"
      }
    },
    "caption": "Interstellar Movie Poster",
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
  "poster": {
    "asset": {
      "sys": {
        "id": "fab3fdc6-89fd-4efa-bfe0-30722fb87661",
        "dataFormat": "asset",
        "contentTypeId": "image"
      }
    },
    "caption": "Interstellar Movie Poster",
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
  "poster": {
    "asset": {
      "sys": {
        "id": "fab3fdc6-89fd-4efa-bfe0-30722fb87661",
        "dataFormat": "asset"
      }
    },
    "caption": "Interstellar Movie Poster",
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