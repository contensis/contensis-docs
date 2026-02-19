## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Workflow Definitions](https://www.contensis.com/help-and-docs/apis/management-http/content/workflow-definitions)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 24 September 2021

## Properties

Name

Type

Format

Description

**id**

string

\-

An identifier for the event group, which must be unique within the workflow.

**name**

object

[localized value](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

The friendly name given to the event group.

## Example

This example shows an event group.

JSON

```
{
    "id": "approveDecline",
    "name": {
        "en-GB": "Approve / decline"
    }
}
```