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

An identifier for the event, which must be unique within the workflow state.

**name**

object

[localized value](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

The friendly name given to the event.

**description**

object

[localized value](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

A description of the event.

**auditText**

object

[localized value](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

The audit text written to the event history log for the event.

**transitionTo**

string

\-

The identifier for the state that the event causes the entry to transition to. If this is not specified or set to \*null\* then the entry will remain in the same state when this event is triggered.

**groupId**

string

\-

The identifier of the workflow \[event group\](event-group) which the event belongs to.

**color**

string

[\-](https://www.contensis.com/help-and-docs/apis/management-http/content/workflow-definitions/workflow-definition-event-button-color)

The color to be displayed in the Contensis UI for the event.

**uiAction**

string

\-

The event to be performed by the Contensis UI when an entry exits the workflow state. Currently on the value "navigateToEntryListing" is supported. The default is for no action to occur.

**parameters**

object\[...\]

[\-](https://www.contensis.com/help-and-docs/apis/management-http/content/workflow-definitions/workflow-definition-event-parameters)

A list of parameters for the event.

**validate**

boolean

field

Specifies if validation should occur when an author invokes this event

## Example

This example shows an event that is part of workflow state (not shown for simplicity).

JSON

```
{
    "id": "submit",
    "name": {
        "en-GB": "Send for approval"
    },
    "auditText": {
        "en-GB": "Submitted"
    },
    "description": {
        "en-GB": "Send the entry for approval"
    },
    "transitionTo": "awaitingApproval",
    "color": "green",
    "groupId": "submitRevoke",
    "uiAction": "navigateToEntryListing",
    "validate": true,
    "parameters": [
        {
            "id": "message",
            "name": {
                "en-GB": "Add an optional message for the approver"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {
                "en-GB": "The message included with the entry submission"
            },
            "default": null,
            "validations": {},
            "editor": {
                "id": "multiline",
                "instructions": {
                    "en-GB": "Optionally include a message to let an approver understand your changes"
                },
                "properties": null
            }
        }
    ]
}
```