## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

## On this page

-   [Properties](#properties)
-   [Example](#example)

A project resource can be retrieved from the Delivery API and could be used to find the languages that the project supports and determine which language is the primary language

## Properties

Name

Type

Format

Description

id

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

name

string

The friendly name given to the project.

description

string

The description text given to a project.

supportedLanguages

string \[…\]

An array of all the languages supported by the project.

primaryLanguage

string

[Language code](/help-and-docs/apis/delivery-js/key-concepts/localization)

The primary language for the project.

## Example

TypeScript

```
// Using TypeScript, or ES Module await syntax
const project = await client.project.get();

console.log(project.name);
console.log(project.primaryLanguage);
console.log(project.supportedLanguages);
```

JavaScript

```
// Using Common JS promise callback syntax
client.project.get()
  .then(function(project) {
    console.log(currentProject.name);
    console.log(currentProject.primaryLanguage);
    console.log(currentProject.supportedLanguages);
  });
```

## On this page

-   [Properties](#properties)
-   [Example](#example)