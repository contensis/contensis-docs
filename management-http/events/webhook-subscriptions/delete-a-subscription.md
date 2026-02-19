1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Events](https://www.contensis.com/help-and-docs/apis/management-http/events)
5.  [Webhook subscriptions](https://www.contensis.com/help-and-docs/apis/management-http/events/webhook-subscriptions)

[Log in to add to favourites](https://www.contensis.com/account/login)

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

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Subscription not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

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