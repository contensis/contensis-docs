1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Integrating with other platforms](https://www.contensis.com/help-and-docs/guides/integrating-with-other-platforms)
4.  Webhooks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 02 October 2024

A webhook is triggered when an event takes place on a Contensis resource. We call these topics. When creating a webhook you need to set the conditions for when the webhook is triggered. A topic can also be filtered to scope the webhook to a particular set of conditions.

## Supported topics

We support the following topics and events.

### Entries: basic events

Event

Description

Created

When an entry is created.

Updated

When an entry is updated.

Published

When an entry is published.

Deleted

When an entry is deleted.

Restored

When an entry is restored.

Archived

When an entry is archived.

Unarchived

When an entry is unarchived.

Filter

Description

Content type(s)

Scope the entries to a particular content type(s).

Content owner

Filter the entries to a specific content owner.

Language(s)

Scope the entries to specific or multiple languages.

Filter

Description

Content type(s)

Scope the entries to a particular content type(s).

Content owner

Filter the entries to a specific content owner.

Language(s)

Scope the entries to specific or multiple languages.

---

### Form responses: basic events

Event

Description

Created

When a form response is created.

Updated

When a form response is updated.

Deleted

When a form response is deleted.

Restored

When a form response is restored.

Archived

When a form response is archived.

Unarchived

When a form response is unarchived.

#### Filters

Filter

Description

Form(s)

Scope the responses to a particular form(s).

Assignee

Filter the responses to a specific assignee.

Language(s)

Scope the responses to specific or multiple languages.

### Form response: workflow events

Workflow events are triggered when a user carries out a particular workflow action on a response. For example, if a team member presses the Read button when viewing a response.

Workflow events are specific to each workflow. This allows you to trigger a webhook for items that have been read/unread in a basic workflow but not from a custom workflow. You can also filter these events further by assigning filters.

#### Filters

Filter

Description

Form(s)

Scope the responses to a particular form(s).

Assignee

Filter the responses to a specific assignee.

Language(s)

Scope the responses to specific or multiple languages.

### Form responses: workflow transition

Workflow transitions are a powerful topic allowing you to understand when content transitions into a specific workflow state.

Workflow transitions can be filtered by the following types.

#### Filters

Filter

Description

Form(s)

Scope the responses to a particular form(s).

Assignee

Filter the responses to a specific assignee.

Language(s)

Scope the responses to specific or multiple languages.

---

### Assets

Event

Description

Created

When an asset is created.

Updated

When an asset is updated.

Deleted

When an asset is deleted.

Published

When an asset is published.

#### Filters

Filter

Description

Asset type(s)

Scope the entries to a particular file type(s).

Language(s)

Scope the entries to specific or multiple languages.

---

### Content types and components

Event

Description

Created

When a content type or component is created.

Updated

When a content type or component is updated.

Deleted

When a content type or component is deleted.

Published

When a content type or component is published.

---

### Nodes

Event

Description

Created

When a node is created.

Updated

When a node is updated or moved.

Deleted

When a node is deleted.

---

### Project

Webhooks are scoped to a project so the only event that is supported is the update event.

Event

Description

Updated

When a node is updated or moved.