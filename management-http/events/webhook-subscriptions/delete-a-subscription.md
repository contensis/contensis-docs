1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Events](/help-and-docs/apis/management-http/events)
5.  [Webhook subscriptions](/help-and-docs/apis/management-http/events/webhook-subscriptions)

[Log in to add to favourites](/account/login)

Page last updated 30 September 2024

DELETE/api/management/projects/**{projectId}**/events/webhooks/subscriptions/**{subscriptionId}**

## Parameters

Name

Parameter type

Type

Format

Description

**projectId***(required)*

path

string

\-

The project identifier found in the project overview screen of the management console.

**subscriptionId***(required)*

path

string

uuid

The unique identifier of the subscription

## Responses

HTTP status code

Reason

Model

**204**

Success

**400**

An invalid payload was sent in the request

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Subscription not found

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Delete a specific webhook subscription for a project

HTTP

```
DELETE: /api/management/projects/movies/events/webhooks/subscriptions/a8badd75-37ef-40c3-ae0f-3a9881165595
```

Expected response

HTTP

```
HTTP Status: 204 No content
```