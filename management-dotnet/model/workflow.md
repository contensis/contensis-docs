1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 28 April 2022

The Workflow object is readonly and contains information about the current workflow state for the entry.Workflow. It also includes details about the previous state transition which resulted in the entry being in the current state along with a list of allowed events that can be invoked by the current user based on their permissions.

## Properties

Name

Type

Description

Id

string

The workflow id that controls the entry life-cycle.

State

string

The id of the state that the entry is currently in.

AllowedEvents

string\[\]

The events that can be invoked by the user based on permissions and the current entry state.

Transition

[WorkflowTransition](#/models/workflowTransition.md)

Details about the previous workflow transition.

## Methods

-   [Invoke(string eventName)](#invoke)
-   [InvokeAsync(string eventName)](#invokeasync)
-   [Invoke(string eventName, Dictionary<string, object=""> data)</string,>](#invoke-with-dictionary)
-   [InvokeAsync(string eventName, Dictionary<string, object=""> data)</string,>](#invokeasync-with-dictionary)
-   [Invoke(string eventName, object data)](#invoke-with-anonymous-object)
-   [InvokeAsync(string eventName, object data)](#invokeasync-with-anonymous-object)

## Invoke

Invokes a named workflow event.

### Syntax

C#

```
public void Invoke(string event)
{
}
```

### Parameters

*event*

Type: string  
The id of the workflow event to invoked, e.g. submit.

### Return value

Type: void

### Example

C#

```
// Submit the entry for approval.
entry.Workflow.Invoke("submit");
```

## InvokeAsync

Invokes a named workflow event asynchronously.

### Syntax

C#

```
public async Task InvokeAsync(string message)
{
}
```

### Parameters

*event*

Type: string  
The id of the workflow event to invoked, e.g. submit.

### Return value

Type: Task

### Example

C#

```
// Submit the entry for approval.
await entry.Workflow.InvokeAsync("submit");
```

## Invoke with Dictionary

Invokes a named workflow event with an optional `Dictionary<string, object>` data parameter.

### Syntax

C#

```
public void Invoke(string event, Dictionary<string, object> data)
{
}
```

### Parameters

*event*

Type: string  
The id of the workflow event to invoked, e.g. submit.

*data*

Type: Dictionary<string, object>  
A dictionary of named data items to include as part of the event invocation.

### Return value

Type: void

### Remarks

The values in the data can only be simple types, i.e. string, int, decimal, datetime, bool. If a complex object type is passed then an `ArgumentException` will be thrown.

### Example

C#

```
// Submit the entry for approval.
entry.Workflow.Invoke("submit", new Dictionary<string, object>
{
    { "message", "Added additional photos to the intro" }
});
```

## InvokeAsync with Dictionary

Invokes a named workflow event asynchronously with an optional `Dictionary<string, object>` data parameter.

### Syntax

C#

```
public async Task InvokeAsync(string message)
{
}
```

### Parameters

*event*

Type: string  
The id of the workflow event to invoked, e.g. submit.

*data*

Type: Dictionary<string, object>  
A dictionary of named data items to include as part of the event invocation.

### Return value

Type: Task

### Remarks

The values in the data can only be simple types, i.e. string, int, decimal, datetime, bool. If a complex object type is passed then an `ArgumentException` will be thrown.

### Example

C#

```
// Submit the entry for approval.
await entry.Workflow.InvokeAsync("submit", 
    new Dictionary<string, object>
    {
        { "message", "Added additional photos to the intro" }
    }
);
```

## Invoke with anonymous object

Invokes a named workflow event with an optional anonymous object data parameter.

### Syntax

C#

```
public void Invoke(string event, object data)
{
}
```

### Parameters

*event*

Type: string  
The id of the workflow event to invoked, e.g. submit.

*data*

Type: object  
An anonymous object to include as part of the event invocation.

### Return value

Type: void

### Remarks

The values in the data can only be simple types, i.e. string, int, decimal, datetime, bool. If a complex object type is passed then an `ArgumentException` will be thrown.

### Example

C#

```
// Submit the entry for approval.
entry.Workflow.Invoke("submit",
    new
    {
        Message = "Added additional photos to the intro"
    };
);
```

## InvokeAsync with anonymous object

Invokes a named workflow event asynchronously with an optional anonymous object data parameter.

### Syntax

C#

```
public async Task InvokeAsync(string message)
{
}
```

### Parameters

*event*

Type: string  
The id of the workflow event to invoked, e.g. submit.

*data*

Type: Dictionary<string, object>  
An object to include as part of the event invocation.

### Return value

Type: Task

### Remarks

The values in the data can only be simple types, i.e. string, int, decimal, datetime, bool. If a complex object type is passed then an `ArgumentException` will be thrown.

### Example

C#

```
// Submit the entry for approval.
await entry.Workflow.InvokeAsync("submit",
    new
    {
        Message = "Added additional photos to the intro"
    };
);
```