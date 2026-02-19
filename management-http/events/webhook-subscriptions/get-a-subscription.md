1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Events](https://www.contensis.com/help-and-docs/apis/management-http/events)
5.  [Webhook subscriptions](https://www.contensis.com/help-and-docs/apis/management-http/events/webhook-subscriptions)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 30 September 2024

GET/api/management/projects/**{projectId}**/events/webhooks/subscriptions/**{subscriptionId}**

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

**200**

Success

[Webhook Subscription](https://www.contensis.com/help-and-docs/apis/management-http/events/webhook-subscriptions)

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

Get a specific webhook subscription.

HTTP

```
GET: /api/management/projects/movies/events/webhooks/subscriptions/0a37d5dd-9408-461d-b09c-3e63d6acfbba
```

Example response

JSON

```
HTTP Status: 200 OK

{
    "id": "0a37d5dd-9408-461d-b09c-3e63d6acfbba",
    "name": "b.g.kahn",
    "description":  "Some updated description",
    "url": "https://mywebservice.com/eventhandler",
    "enabled": true,
    "topics": [
        {
            "resourceType": "entry",
            "event": [
                "created"
            ],
            "contentTypeId": [
                "blog"
            ],
            "language": [
                "en-GB"
            ],
            "owner": "t.durden"
        },
        {
            "resourceType": "entry",
            "event": [
                "updated"
            ],
            "contentTypeId": [
                "blog"
            ],
            "language": [
                "en-GB"
            ],
            "owner": "t.durden"
        },
        {
            "resourceType": "contentType",
            "event": [
                "created"
            ]
        }
    ],
    "templates": {},
    "headers": {},
    "version": {
        "createdBy": "stub user",
        "created": "2020-11-25T09:49:36.568912Z",
        "modifiedBy": "stub user",
        "modified": "2020-11-25T09:53:49.9189103Z",
        "versionNo": "2.0"
    }
}
```