1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model
5.  Workflow definitions

[Log in to add to favourites](/account/login)

Page last updated 17 December 2020

An action which is performed on an entry when it enters or leaves a workflow state. Entry actions are specified in the workflow [state](state) and exit actions are specified in the workflow state [event](event).

## Supported actions

The following list contains the actions that are currently supported:

Exit action

Description

validateEntry

Causes the entry's fields to be validated.

publishEntry

Causes the entry to be published.

updateEntry

Causes the entry to be updated and any changes to be saved.

## Examples

The permitted actions are:

JSON

```
{
    "invokeAction": "validateEntry"
}
```

JSON

```
{
    "invokeAction": "publishEntry"
}
```

JSON

```
{
    "invokeAction": "updateEntry"
}
```