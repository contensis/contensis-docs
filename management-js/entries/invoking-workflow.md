1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Entries

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Workflow events can be invoked for a specific entry by passing the event name and the event data.

***invokeWorkflow(entry: Entry, event: string, data?: any): Promise<Entry>***

## Parameters

Name

Type

Format

Description

entry

object

[Entry](https://www.contensis.com/help-and-docs/apis/management-js/model/entry)

The entry object.

event

string

The event type, as described at [Workflow](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/workflow)

data?

object

The optional event data.

## Returns

A Promise that will resolve with an [Entry](https://www.contensis.com/help-and-docs/apis/management-js/model/entry) object.

## Example

JavaScript

```
client.entries.invokeWorkflow(existingEntry, 'draft.publish')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

Workflow events can be invoked for a specific entry by passing a workflow trigger object. This method allows more flexibility than *invokeWorkflow* as you can omit the language and the version number if not required. You should use this method when you need to unpublish an entry, like in the example below.

***invokeWorkflowByTrigger(entry: Entry, workflowTrigger: WorkflowTrigger): Promise<Entry>***

## Parameters

Name

Type

Format

Description

entry

object

[Entry](https://www.contensis.com/help-and-docs/apis/management-js/model/entry)

The entry object.

workflowTrigger

object

[WorkflowTrigger](https://www.contensis.com/help-and-docs/apis/management-js/model/workflow-trigger)

The workflow trigger object type.

## Returns

A Promise that will resolve with an [Entry](https://www.contensis.com/help-and-docs/apis/management-js/model/entry) object.

## Example

JavaScript

```
   client.entries.invokeWorkflowByTrigger(existingEntry, {
    event: 'sysUnpublish',
    language: 'en-GB'
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```