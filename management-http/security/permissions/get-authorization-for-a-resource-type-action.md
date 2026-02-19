## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [Permissions overview](/help-and-docs/apis/management-http/security/permissions)

[Log in to add to favourites](/account/login)

Page last updated 31 January 2025

Gets an authorization confirmation for the requested user, resource type and action.

GET /api/management/projects/**{projectId}**/security/permissions/**{resourceType}**/actions/**{action}**?userId=**{userId}**

## Parameters

Name

Parameter type

Type

Format

projectId

path

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

resourceType

path

string

The type of resource to retrieve permissions for. Permitted values are: assets, audiences, blocks, comments, contenttypes, domains, entries, eventstreams, forms, manifests, nodes, proxies, redirects, renderers, signals, views, webhooksubscriptions

action

path

string

Name of the action to check authorization for. The possible actions are:

userId

query

string

The optional id of the user to check authorization for.

Example request

JSON

```
GET: /api/management/projects/movieDb/security/permissions/webhookSubscriptions/actions/create/?userId=a.user
```

### Response message

HTTP status code

Reason

Response model

200

The action is authorized

Authorized true

404

Not authorized for action

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

500

InternalServerError

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

Example request

JSON

```
{
    "authorized": true
}
```