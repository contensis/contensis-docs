1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Key concepts

[Log in to add to favourites](/account/login)

Page last updated 09 December 2024

## Overview

An entry's life-cycle is controlled by the workflow assigned to the content type that the entry is based on. Contensis supports two standard built-in workflows types.

### Basic workflow

Allows content to be authored and then published instantly.

![Basic workflow](/image-library/resources-images/developer-documentation-images/basic-workflow.x8cd8e7f9.png?q=80&f=webp)

### Approval workflow

Allows content to be submitted for approval so that it is controlled by an authorised approver before it is made live.

![Approval workflow](/image-library/resources-images/developer-documentation-images/approval-workflow.x70f20142.png?q=80&f=webp)

Entries are by default controlled by the *basic* workflow, but this can be changed by specifying a different workflow type in the content type editing screen.

## Invoking events

Workflow events can be invoked by POST'ing a [workflow trigger](/help-and-docs/apis/management-js/model/workflow-trigger) to the workflow events resource for an entry.

### Example

JSON

```
{
    "language": "en-GB",
    "version": "2.3",
    "event": "draft.submit",
    "data": {
        "message": "Have updated the final paragrah"
    }
}
```

The eventName parameter follows the structure:

`{workflowStateId}.{workflowEventId}`

These are the available events for the supported workflows

### Basic workflow

-   draft.publish

### Approval workflow

-   draft.submit
-   awaitingApproval.approve
-   awaitingApproval.decline
-   awaitingApproval.revoke
-   declined.submit

It is possible to only specify the `workflowEventId` i.e. 'approve' or 'submit' and the Management API client will automatically prefix the current state of the entry, but this is less explicit and open to invalid event invocations.

**If a workflow event is invoked that is not valid for the current state, then a `WorkflowException` will be raised detailing the invalid action.**

It is important to note certain states have 'sysUpdate' and 'sysDelete' events, which can't be invoked directly through a workflow event invocation, but can be invoked using the entry POST and DELETE operations. When an entry is in the Published state, invoking an entry POST update (which in-turn invokes sysUpdate) will automatically move the state back to Draft.

## Event permissioning

The invocation of workflow events is controlled by the roles & permissions security API, which can be configured within the Contensis Roles screens. Individual events can be permissioned so that granular control is possible, ensuring each step of a workflow is only invocable by an authorized user. If authorization is denied when invoking a workflow event then a 403 response is returned.