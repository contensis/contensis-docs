1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 28 April 2022

Event methods specific to the standard Contensis workflows can be included to make using the API simpler. These are implemented as methods using [extension methods](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/extension-methods) and can be imported by using the appropriate namespaces for the target workflow.

**Basic workflow**

-   [Publish(this Workflow workflow)](#publish)
-   [PublishAsync(this Workflow workflow)](#publishasync)
-   [Unpublish(this Workflow workflow, bool unpublishAll = false)](#unpublish)
-   [UnpublishAsync(this Workflow workflow, bool unpublishAll = false)](#unpublishasync)

**Approval workflow**

-   [Submit(this Workflow workflow, string message)](#submit)
-   [SubmitAsync(this Workflow workflow, string message)](#submit)
-   [Approve(this Workflow workflow)](#approve)
-   [ApproveAsync(this Workflow workflow)](#approveasync)
-   [Decline(this Workflow workflow, string message)](#decline)
-   [DeclineAsync(this Workflow workflow, string message)](#declineasync)
-   [Revoke(this Workflow workflow)](#revoke)
-   [RevokeAsync(this Workflow workflow)](#revokeasync)
-   [Unpublish(this Workflow workflow, bool unpublishAll = false)](#unpublish)
-   [UnpublishAsync(this Workflow workflow, bool unpublishAll = false)](#unpublishasync)

Adding the following namespace declaration will add the Publish methods.

C#

```
using Zengenti.Contensis.Management.Workflow.Basic;
```

## Publish

Publishes an entry instance for entries in the Contensis basic workflow.

### Syntax

C#

```
public static void Publish(this Workflow workflow)
{
}
```

### Return value

Type: void

### Remarks

On a successful publish, the entry instance is updated with the new version details controlled from the service. A WorkflowException will be thrown if there is any issue with the publish workflow state change. Other exception types could be thrown if there are any data validation issues, unexpected issue in the service or a local exception.

### Example

C#

```
// Publish the version of the entry.
entry.Workflow.Publish();
```

## PublishAsync

Publishes an entry instance asynchronously for entries in the Contensis basic workflow.

### Syntax

C#

```
public async Task PublishAsync(this Workflow workflow)
{
}
```

### Return value

Type: Task

### Remarks

On a successful publish, the entry instance is updated with the new version details controlled from the service. A WorkflowException will be thrown if there is any issue with the publish workflow state change. Other exception types could be thrown if there are any data validation issues, unexpected issue in the service or a local exception.

### Example

C#

```
// Publish the version of the entry.
await entry.Workflow.PublishAsync();
```

Adding the following namespace declaration will add the Publish methods.

C#

```
using Zengenti.Contensis.Management.Workflow.Approval;
```

## Submit

Submits an entry instance to the awaiting approval state for entries in the Contensis approval workflow.

### Syntax

C#

```
public static void Submit(this Workflow workflow, string message = null)
{
}
```

### Parameters

*message*

Type: string  
An optional message that can be included with the entry submission.

### Return value

Type: void

### Example

C#

```
// Submit the entry for approval.
entry.Workflow.Submit("I've updated the 2nd paragraph to make it clearer");
```

## SubmitAsync

Submits an entry instance to the awaiting approval state asynchronously for entries in the Contensis approval workflow.

### Syntax

C#

```
public static async Task SubmitAsync(this Workflow workflow, string message = null)
{
}
```

### Parameters

*message*

Type: string  
An optional message that can be included with the entry submission.

### Return value

Type: Task

### Example

C#

```
// Submit the entry for approval asynchronously.
await entry.Workflow.SubmitAsync("I've updated the 2nd paragraph to make it clearer");
```

## Approve

Approves an entry for publishing for entries in the Contensis approval workflow.

### Syntax

C#

```
public void Approve(this Workflow workflow)
{
}
```

### Return value

Type: void

### Example

C#

```
// Approve the entry for publishing.
entry.Workflow.Approve();
```

## ApproveAsync

Approves an entry for publishing asynchronously for entries in the Contensis approval workflow.

### Syntax

C#

```
public async Task ApproveAsync(this Workflow workflow)
{
}
```

### Return value

Type: Task

### Example

C#

```
// Approve the entry instance asynchronously.
await entry.Workflow.ApproveAsync();
```

## Decline

Declines an entry submission for entries in the Contensis approval workflow.

### Syntax

C#

```
public void Decline(this Workflow workflow, string message = null)
{
}
```

### Parameters

*message*

Type: string  
An optional message that can be included to detail the decline reason.

### Return value

Type: void

### Example

C#

```
// Decline the entry submission.
entry.Workflow.Decline("There are multiple spelling mistakes in the opening paragraph");
```

## DeclineAsync

Declines an entry submission for entries in the Contensis approval workflow.

### Syntax

C#

```
public async Task DeclineAsync(this Workflow workflow, string message)
{
}
```

### Parameters

*message*

Type: string  
An optional message that can be included to detail the decline reason.

### Return value

Type: Task

### Example

C#

```
// Decline the entry submission asynchronously.
await entry.Workflow.DeclineAsync("I've updated the 2nd paragraph to make it clearer");
```

## Revoke

Revokes an entry submission for entries in the Contensis approval workflow.

### Syntax

C#

```
public void Revoke(this Workflow workflow)
{
}
```

### Return value

Type: void

### Example

C#

```
// Revoke the entry submission.
entry.Workflow.Revoke();
```

## RevokeAsync

Revokes an entry submission for entries asynchronously in the Contensis approval workflow.

### Syntax

C#

```
public async Task RevokeAsync(this Workflow workflow)
{
}
```

### Return value

Type: Task

### Example

C#

```
// Revoke the entry submission asynchronously.
await entry.Workflow.RevokeAsync();
```

---

Adding either one of the following namespace declarations will add the Unpublish methods.

C#

```
using Zengenti.Contensis.Management.Workflow.Approval;
using Zengenti.Contensis.Management.Workflow.Basic;
```

## Unpublish

Unpublishes an entry.

### Syntax

C#

```
public void Unpublish(this Workflow workflow, bool unpublishAll = false)
{
}
```

### Parameters

*unpublishAll*

Type: boolean  
An optional boolean specifying whether all language variations of the entry should be unpublished too.

### Return value

Type: void

### Example

C#

```
// Unpublish the current entry.
entry.Workflow.Unpublish();

// Unpublish all of the language variations for this entry.
entry.Workflow.Unpublish(true);
```

## UnpublishAsync

Unpublishes an entry asynchronously.

### Syntax

C#

```
public async Task UnpublishAsync(this Workflow workflow, bool unpublishAll = false)
{
}
```

### Parameters

*unpublishAll*

Type: boolean  
An optional boolean specifying whether all language variations of the entry should be unpublished too.

### Return value

Type: Task

### Example

C#

```
// Unpublish the current entry.
await entry.Workflow.UnpublishAsync();

// Unpublish all of the language variations for this entry.
await entry.Workflow.UnpublishAsync(true);
```