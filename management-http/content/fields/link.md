## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Fields](https://www.contensis.com/help-and-docs/apis/management-http/content/fields)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 09 February 2024

## Properties

Name

Type

Format

Description

**sys**

object

\-

The link system data

**sys.id**

string

uuid

The identifier of the referenced entry or asset

**sys.dataFormat**

string

\-

Either entry or asset

**sys.contentTypeId**

string

\-

The content type ID of the linked entry or asset

**sys.language**

string

language

The target language of the entry variation

## Example

JSON

```
{
    "sys": {
        "dataFormat": "asset",
        "contentTypeId": "image",
        "language": "en-GB",
        "id": "639f00f2-800f-41e6-9713-c57d925fface"
    }
}
```

Management Example

JSON

```
{
    "sys": {
        "dataFormat": "asset",
        "contentTypeId": "image",
        "language": "en-GB",
        "id": "639f00f2-800f-41e6-9713-c57d925fface"
    }
}
```

Delivery example

JSON

```
{
    "sys": {
        "dataFormat": "asset",
        "contentTypeId": "image",
        "language": "en-GB",
        "id": "639f00f2-800f-41e6-9713-c57d925fface",
        "uri": "/image-library/people-images/al-pacino.x30cc3dd3.jpg"
    }
}
```