1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model
5.  Workflow definitions

[Log in to add to favourites](/account/login)

Page last updated 17 December 2020

Groups which [events](event) in workflow [states](state) are assigned to. These group functionally similar transitions between states (e.g. *save*, *approveDecline*, *delete*).

## Properties

Name

Type

Format

Description

id

string

An identifier for the event group, which must be unique within the workflow.

name

object

[Localized value](/help-and-docs/apis/management-js/key-concepts/localization)

The friendly name given to the event group.

## Example

This example shows an event group.

JSON

```
{
    "id": "save",
    "name": {
        "en-GB": "Save"
    }
}
```