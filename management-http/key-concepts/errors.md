## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Key Concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 21 June 2021

## Properties

Name

Type

Format

Description

**logId**

string

uuid

This can be used within the Contensis log search to understand further details about the error.

**message**

string

\-

A description of the error.

**data**

any

\-

An object containing specific data relevant to the error.

**type**

string

\-

The type of error - for the Delivery API, this will always be error.

## Example

JSON

```
{
  "logId": "63cb1df0-b82a-459e-accc-635e187f3b8b",
  "message": "An error occurred requesting the entry",
  "data": {
      "entryId": "ba8a92bd-0e5f-465e-acec-3cdb3db38df6",
      "projectId": "movieDb"
  },
  "type": "error"
}
```

Example error response

JSON

```
{
  "logId": "63cb1df0-b82a-459e-accc-635e187f3b8b",
  "message": "An error occurred requesting the entry",
  "data": {
      "entryId": "ba8a92bd-0e5f-465e-acec-3cdb3db38df6",
      "projectId": "movieDb"
  },
  "type": "error"
}
```

Example error response

JSON

```
{
  "logId": "63cb1df0-b82a-459e-accc-635e187f3b8b",
  "message": "An error occurred requesting the entry",
  "data": {
      "entryId": "ba8a92bd-0e5f-465e-acec-3cdb3db38df6",
      "projectId": "movieDb"
  },
  "type": "error"
}
```