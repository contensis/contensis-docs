JSON

```
{
    "projectId": "website",
    "name": "Movie Editors",
    "description": "Movie editors can carry out all actions with the exception of deleting entries",
    "enabled": true,
    "permissions": {
        "contentTypes": [],
        "entries": [
            {
                "languages": [
                    "en-GB"
                ],
                "id": "movie",
                "actions": [
                    "contensisEntryApproval.sysCreate",
                    "contensisEntryApproval.draft.submit",
                    "contensisEntryApproval.draft.sysUpdate",
                    "contensisEntryApproval.draft.sysClearPublishSchedule",
                    "contensisEntryApproval.draft.sysSetPublishSchedule",
                    "contensisEntryApproval.draft.sysClearUnpublishSchedule",
                    "contensisEntryApproval.draft.sysSetUnpublishSchedule",
                    "contensisEntryApproval.awaitingApproval.revoke",
                    "contensisEntryApproval.awaitingApproval.decline",
                    "contensisEntryApproval.awaitingApproval.approve",
                    "contensisEntryApproval.awaitingApproval.scheduledApprove",
                    "contensisEntryApproval.awaitingApproval.sysClearPublishSchedule",
                    "contensisEntryApproval.awaitingApproval.sysSetPublishSchedule",
                    "contensisEntryApproval.awaitingApproval.sysClearUnpublishSchedule",
                    "contensisEntryApproval.awaitingApproval.sysSetUnpublishSchedule",
                    "contensisEntryApproval.declined.submit",
                    "contensisEntryApproval.declined.sysUpdate",
                    "contensisEntryApproval.declined.sysClearPublishSchedule",
                    "contensisEntryApproval.declined.sysSetPublishSchedule",
                    "contensisEntryApproval.declined.sysClearUnpublishSchedule",
                    "contensisEntryApproval.declined.sysSetUnpublishSchedule",
                    "contensisEntryApproval.scheduled.cancel",
                    "contensisEntryApproval.scheduled.publishNow",
                    "contensisEntryApproval.scheduled.sysPublishScheduleInvoke",
                    "contensisEntryApproval.scheduled.sysSetPublishSchedule",
                    "contensisEntryApproval.scheduled.sysClearUnpublishSchedule",
                    "contensisEntryApproval.scheduled.sysSetUnpublishSchedule",
                    "contensisEntryApproval.versionComplete.sysUpdate",
                    "contensisEntryApproval.versionComplete.sysClearPublishSchedule",
                    "contensisEntryApproval.versionComplete.sysSetPublishSchedule",
                    "contensisEntryApproval.versionComplete.sysClearUnpublishSchedule",
                    "contensisEntryApproval.versionComplete.sysSetUnpublishSchedule",
                    "contensisEntryApproval.sysUnpublish"
                ]
            }
        ],
        "assets": [
            {
                "languages": [
                    "*"
                ],
                "id": "pdf",
                "actions": [
                    "*"
                ]
            }
        ],
        "webhookSubscriptions": {
            "actions": [
                "create",
                "view"
            ]
        },
        "proxies": {
            "actions": [
                "create",
                "update",
                "publish"
            ]
        },
        "eventStreams": {
            "actions": [
                "connect",
                "useCustomTemplates"
            ]
        },
        "blocks": {
            "actions": []
        },
        "renderers": {
            "actions": []
        }
    },
    "assignments": {
        "users": [
            "a.user"
        ],
        "groups": [
            "Movie editors"
        ],
        "apiKeys": [
            "Movie Import"
        ]
    }
}
```