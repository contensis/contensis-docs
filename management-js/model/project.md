1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

A project resource can be retrieved from the Delivery API to understand the languages that the project supports and which language is the primary language.

## Properties

Name

Type

Format

Description

id

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console

name

string

The friendly name given to the project

description

string

The description text given to a project

supportedLanguages

string \[…\]

An array of all the languages supported by the project

primaryLanguage

string

[Language code](https://www.contensis.com/help-and-docs/apis/management-js/localization)

The primary language for the project

color

string

[Color](https://www.contensis.com/help-and-docs/apis/management-js/model/colors)

The color to be displayed in the Contensis UI for the project

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