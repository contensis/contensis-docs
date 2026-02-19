## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Events](/help-and-docs/apis/management-http/events)
5.  [Webhook subscriptions](/help-and-docs/apis/management-http/events/webhook-subscriptions)

[Log in to add to favourites](/account/login)

Page last updated 30 September 2024

GET/api/management/projects/**{projectId}**/events/webhooks/subscriptions

## Parameter

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

## Responses

HTTP status code

Reason

Model

**200**

Success

[Webhook Subscription](/help-and-docs/apis/management-http/events/webhook-subscriptions)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get a list webhook subscriptions

HTTP

```
GET: /api/management/projects/movies/events/webhooks/subscriptions
```