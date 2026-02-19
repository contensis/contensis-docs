Update entries basic events subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Update entries basic events subscription",
    "description": "An example update of entries basic events subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "entry",
            "event": [
                "created",
                "updated",
                "deleted",
                "published",
                "unpublished",
                "archived",
                "unarchived",
                "restored"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update entries workflow events subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Update entries workflow events subscription",
    "description": "An example update of entries workflow events subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "entry",
            "event": [
                "workflowEventRaised"
            ],
            "contentTypeId": [
                "book"
            ],
            "owner": "some.username",
            "workflowEvent": [
                "contensisEntryApproval.draft.submit",
                "contensisEntryApproval.draft.submitAndApprove",
                "contensisEntryApproval.draft.submitAndScheduledApprove",
                "contensisEntryApproval.awaitingApproval.revoke",
                "contensisEntryApproval.awaitingApproval.decline",
                "contensisEntryApproval.awaitingApproval.approve",
                "contensisEntryApproval.awaitingApproval.scheduledApprove",
                "contensisEntryApproval.declined.submit",
                "contensisEntryApproval.scheduled.cancel",
                "contensisEntryApproval.scheduled.publishNow"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST"
}
```

Update entries workflow transition events subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Update entries workflow transition subscription",
    "description": "An example update of entries workflow transition subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "entry",
            "event": [
                "workflowStateChanged"
            ],
            "contentTypeId": [
                "book"
            ],
            "owner": "some.username",
            "workflowState": [
                "contensisEntryApproval.draft",
                "contensisEntryApproval.awaitingApproval",
                "contensisEntryApproval.declined",
                "contensisEntryApproval.scheduled",
                "contensisEntryApproval.versionComplete",
                "contensisEntryApproval.archived"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST"
}
```

Update form response basic events subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Update form response basic events subscription",
    "description": "An example update of form response basic events subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "form",
            "event": [
                "created",
                "updated",
                "deleted",
                "archived",
                "unarchived",
                "restored"
            ],
            "contentTypeId": [
                "someForm"
            ],
            "owner": "some.username"
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST"
}
```

Update form response workflow events subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example form response workflow events subscription",
    "description": "An example form response workflow events subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
         {
            "resourceType": "form",
            "event": [
                "workflowEventRaised"
            ],
            "contentTypeId": [
                "someForm"
            ],
            "owner": "some.username",
            "workflowEvent": [
                "contensisFormBasic.unread.read",
                "contensisFormBasic.read.unread"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST"
}
```

Update form response workflow transition subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Form response workflow transition subscription",
    "description": "An example update of form response workflow transition subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "form",
            "event": [
                "workflowStateChanged"
            ],
            "contentTypeId": [
                "someForm"
            ],
            "owner": "some.username",
            "workflowState": [
                "contensisFormBasic.unread",
                "contensisFormBasic.read",
                "contensisFormBasic.archived"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST"
}
```

Update assets subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update asset subscription",
    "description": "An example update asset subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "asset",
            "event": [
                "created",
                "updated",
                "deleted",
                "published"
            ],
            "contentTypeId": [
                "image"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update content types/forms subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update contenttype/form subscription",
    "description": "An example update of content type/form subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "contentType",
            "event": [
                "created",
                "updated",
                "deleted",
                "published"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update components subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update component subscription",
    "description": "An example update of component subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "component",
            "event": [
                "created",
                "updated",
                "deleted",
                "published"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update nodes subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update nodes subscription",
    "description": "An example update of a nodes subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "node",
            "event": [
                "created",
                "updated",
                "deleted",
                "moved",
                "childOrderChanged"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update projects subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update projects subscription",
    "description": "An example update of projects subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "project",
            "event": [
                "updated"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update users subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update users subscription",
    "description": "An example update of users subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "user",
            "event": [
                "created",
                "updated",
                "deleted"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update user groups subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update groups subscription",
    "description": "An example update of groups subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "group",
            "event": [
                "created",
                "updated",
                "deleted",
                "userAdded",
                "userRemoved",
                "groupAdded",
                "groupRemoved"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```

Update comments for entries subscription

JSON

```
PUT: /api/management/projects/movies/events/webhooks/subscriptions/{subscriptionId}

{
    "name": "Example update comments for entries subscription",
    "description": "An example update of comments for entries subscription",
    "url": "https://webhook.site/11ac515d-bba8-462d-8da3-f4a8312a6745",
    "enabled": true,
    "topics": [
        {
            "resourceType": "comment.entry",
            "event": [
                "created",
                "replied",
                "updated",
                "resolved",
                "reactivated",
                "deleted"
            ]
        }
    ],
    "version": {
        "versionNo": {Must be the current version number - e.g. '12.0'}
    },
    "templates": {},
    "headers": {},
    "method": "POST",
    "ui": false
}
```