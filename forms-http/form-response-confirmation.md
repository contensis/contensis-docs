## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Forms API](https://www.contensis.com/help-and-docs/apis/forms-http)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

When you submit a form response through the Forms API, the API returns the following payload:

Name

Type

Format

Description

**confirmation**

object

\-

Contains the result of the confirmation rule triggered.

**form**

object

\-

Contains the form submission details.

**form.fieldName**

any

\-

A property for each field submitted by the user. i.e. emailAddress, name, mobileNumber, typeOfEnquiry and enquiry

**sys**

object

\-

System metadata related to the submission.

**sys.id**

string

uuid

The unique ID of the form entry created.

**sys.dataFormat**

string

dataFormat

The data format of the submission, in the case of a form this will always be form

**sys.language**

string

language code

The language of the submission

### Example of a form response confirmation

JSON

```
{
  "confirmation": {
    "content": "<p>Thanks for your FOI request. We aim to respond to all FOI requests within 72 hours.</p>"
  },
  "form": {
    "emailAddress": "emily.dawson@fictionalcorp.com",
    "enquiry": null,
    "mobileNumber": "07123 987654",
    "name": "Emily Dawson",
    "reference": "EF 0227 0144 0067",
    "typeOfEnquiry": "request-for-information",
    "entryTitle": "EF 0227 0144 0067",
    "entryDescription": null,
    "sys": {
      "id": "3d5d6498-1fb4-4d2a-8973-493a9f0ac6b8",
      "dataFormat": "form",
      "language": "en-GB"
    }
  }
}
```

### Confirmation object: variants

The confirmation object returned depends on the type of confirmation configured in the content type.

#### 1\. HTML content

If the confirmation is an HTML message, the `content` field contains the formatted message:

JSON

```
{
  "confirmation": {
    "content": "<p>Thanks for your FOI request. We aim to respond to all FOI requests within 72 hours.</p>"
  }
}
```

#### 2\. URL redirect

If a redirect is configured, the `link` field provides the target URI:

JSON

```
{
  "confirmation": {
    "link": {
      "sys": {
        "uri": "/en-gb/books/billy-and-the-minpins"
      }
    }
  }
}
```

-   **link.sys.uri**: The URL to which the user should be redirected to after form submission.