## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 14 January 2022

## Properties

Name

Type

Format

Description

Example

**id**

string

\-

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console

**name**

string

\-

The friendly name given to the project

**description**

string

\-

The description text given to a project

**supportedLanguages**

string\[...\]

[language code](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

An array of all the languages supported by the project

**primaryLanguage**

string

[language code](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

The primary language for the project

**deliverySysExclusions**

string\[...\]

\-

Allows fields in the sys object to be excluded from the delivery entry response, simplifying the data returned and reducing the payload. The following fields cannot be excluded sys.versionStatus, sys.id, sys.ur, sys.language, sys.dataFormat and sys.contentTypeId

sys.owner, sys.version.\*

## Example

JSON

```
{
    "id": "movieDb",
    "name": "Movie Database",
    "description": "...",
    "supportedLanguage": [
        "en-GB",
        "en-US",
        "fr"
    ],
    "primaryLanguage": "en-GB"
}
```

JSON

```
{
    "id": "movieDb",
    "name": "Movie Database",
    "description": "...",
    "supportedLanguage": [
        "en-GB",
        "en-US",
        "fr"
    ],
    "primaryLanguage": "en-GB",
    "deliverySysExclusions": [
         "sys.owner"
    ]
}
```

JSON

```
{
    "id": "movieDb",
    "name": "Movie Database",
    "description": "...",
    "supportedLanguage": [
        "en-GB",
        "en-US",
        "fr"
    ],
    "primaryLanguage": "en-GB"
}
```

## Remarks

Changes to the deliverySysExclusions may take up to an hour to be reflected in the delivery API. This is by design, the change propagates as the cache expires on entries rather than forcing an entire site cache purge.