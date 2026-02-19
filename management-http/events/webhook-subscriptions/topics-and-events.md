1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Events](https://www.contensis.com/help-and-docs/apis/management-http/events)
5.  [Webhook subscriptions](https://www.contensis.com/help-and-docs/apis/management-http/events/webhook-subscriptions)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 30 September 2024

## Properties

Name

Type

Format

Description

**resourceType**

string

\-

The type of resource events to subscribe to. See 'Remarks' section for available values.

**event**

string

\-

The type of event to subscribe to. See 'Remarks' section for available values.

**contentTypeId**

string

\-

Subscribe to events for a specific content type. Used when subscribing to events for a resource type whose instances have a contentTypeId property.

**id**

string

uuid

Subscribe to events for a specific instance. Used when subscribing to events for a resource type whose instances have an id property.

**dataFormat**

string

\-

Subscribe to events for a specific data format. Used when subscribing to events for a resource type whose instances have a dataFormat property.

**owner**

string

\-

Subscribe to events for a specific content owner. Used when subscribing to events for a resource type whose instances have an owner property.

**workflowStateChanged**

string

\-

Subscribe to events where the workflow state changed. Used when subscribing to events for a resource type whose instances go through a workflow.

**workflowEventRaised**

string

\-

Subscribe to events where a work flow event has been raised. Used when subscribing to events for a resource type whose instances go through a workflow.

**workflowState**

string

\-

When subscribing to workflow state changes, restrict a subscription to events for a specific state. Used when subscribing to the workflowStateChanged events for a resource type whose instances go through a workflow.

**workflowEventRaised**

string

\-

When subscribing to workflow events, restrict a subscription to specific workflow events. Used when subscribing to the workflowEventRaised events for a resource type whose instances go through a workflow.

## Example

An example of Topics used in an webhook subscription

JSON

```
{
    "id": "3a7ce8e3-9c9f-4242-be20-35edb29c4a07",
    "name": "Content sync",
    "invokeUrl": "https://external.mywebsite.com/handlewebhooks",
    "enabled": true,
    "topics": [
        {
            "resourceType": "entry",
            "event": "updated",
            "language": "fr-fr",
            "contentTypeId": "blog",
            "owner": "t.durden"
        },
        {
            "resourceType": "entry",
            "event": "published",
            "contentTypeId": "news",
            "owner": "t.durden"
        },
        {
            "resourceType": "contentType",
            "event": "created"
        }
    ]
}
```

## Remarks

#### Topics schema

Resource type

Associated topic properties

Notes

entry/asset

-   contentType
-   event
    -   created
    -   updated
    -   deleted
    -   published
    -   unpublished
    -   archived
    -   unarchived
    -   restored
    -   workflowEvent
        -   contensisEntryApproval.draft.submit
        -   contensisEntryApproval.draft.submitAndApprove
        -   contensisEntryApproval.draft.submitAndScheduledApprove
        -   contensisEntryApproval.awaitingApproval.revoke
        -   contensisEntryApproval.awaitingApproval.decline
        -   contensisEntryApproval.awaitingApproval.approve
        -   contensisEntryApproval.awaitingApproval.scheduledApprove
        -   contensisEntryApproval.declined.submit
        -   contensisEntryApproval.scheduled.cancel
        -   contensisEntryApproval.scheduled.publishNow
    -   workflowState
        -   contensisEntryApproval.draft
        -   contensisEntryApproval.awaitingApproval
        -   contensisEntryApproval.declined
        -   contensisEntryApproval.scheduled
        -   contensisEntryApproval.versionComplete
        -   contensisEntryApproval.archived
-   language
-   project

Semi-dependent parameters:

-   workflowStateChanged => workflowState
-   workflowEventRaised => workflowEvent

form

-   form
-   event
    -   created
    -   updated
    -   deleted
    -   archived
    -   unarchived
    -   restored
    -   workflowEventRaised
        -   contensisFormBasic.unread.read
        -   contensisFormBasic.read.unread
    -   workflowStateChanged
        -   contensisFormBasic.unread
        -   contensisFormBasic.read
        -   contensisFormBasic.archived
-   language
-   project

Semi-dependent parameters:

-   workflowStateChanged => workflowState
-   workflowEventRaised => workflowEvent

contentType/component

-   event
    -   created
    -   updated
    -   deleted

 

node

-   event
    -   created
    -   updated
    -   deleted

 

project

-   event
    -   updated

 

user

-   event
    -   created
    -   updated
    -   deleted

 

group

-   event
    -   created
    -   updated
    -   deleted
    -   userAdded
    -   userRemoved
    -   groupAdded
    -   groupRemoved

 

comment.entry

-   event
    -   created
    -   replied
    -   updated
    -   resolved
    -   reactivated
    -   deleted