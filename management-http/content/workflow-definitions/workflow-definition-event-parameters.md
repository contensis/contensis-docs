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

The identifier for the parameter.

**name**

object

[localized value](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

The friendly name given to the parameter.

**description**

object

[localized value](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

The description given to the parameter.

**dataType**

string

\-

This should be set to "string".

**default**

object

\-

This should be set to null.

**validations**

object\[...\]

[validation](https://www.contensis.com/help-and-docs/apis/management-http/content/workflow-definitions/workflow-definition-event-validation)

The validation to be used.

**editor**

object

[editor](https://www.contensis.com/help-and-docs/apis/management-http/content/workflow-definitions/workflow-definition-event-editor)

The editor to be used.

## Example

This example shows a parameter as used in a workflow definition.

JSON

```
{
  "id": "decline",
  "name": {
    "en-GB": "Decline"
  },
  "auditText": {
    "en-GB": "Declined"
  },
  "description": {
    "en-GB": "Decline the entry for approval"
  },
  "transitionTo": "declined",
  "color": "red",
  "groupId": "approveDecline",
  "uiAction": "navigateToEntryListing",
  "validate": false,
  "parameters": [
    {
      "id": "message",
      "name": {
        "en-GB": "Add a message to explain to the author why this content is being declined"
      },
      "dataType": "string",
      "dataFormat": null,
      "description": {
        "en-GB": "The decline reason"
      },
      "default": null,
      "validations": {
        "required": {
          "message": {
            "en-GB": "The decline reason is required"
          }
        }
      },
      "editor": {
        "id": "multiline",
        "instructions": {
          "en-GB": "Include a message to let an approver know your changes"
        },
        "properties": null
      }
    }
  ]
}
```