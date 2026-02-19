JSON

```
{
    "id": "awaitingApproval",
    "name": {
        "en-GB": "Awaiting approval"
    },
    "events": [
        {
            "id": "revoke",
            "name": {
                "en-GB": "Revoke and edit"
            },
            "auditText": {
                "en-GB": "Revoked"
            },
            "description": {
                "en-GB": "Revoke the entry submission"
            },
            "transitionTo": "draft",
            "color": "white",
            "groupId": "submitRevoke",
            "uiAction": "none",
            "validate": false,
            "parameters": []
        },
        {
            "id": "decline",
            "name": {
                "en-GB": "Decline"
            },
            "auditText": {
                "en-GB": "Declined"
            },
            "description": {
                "en-GB": "Decline the entry for approval"
            },
            "transitionTo": "declined",
            "color": "red",
            "groupId": "approveDecline",
            "uiAction": "navigateToEntryListing",
            "validate": false,
            "parameters": [
                {
                    "id": "message",
                    "name": {
                        "en-GB": "Add a message to explain to the author why this content is being declined"
                    },
                    "dataType": "string",
                    "dataFormat": null,
                    "description": {
                        "en-GB": "The decline reason"
                    },
                    "default": null,
                    "validations": {
                        "required": {
                            "message": {
                                "en-GB": "The decline reason is required"
                            }
                        }
                    },
                    "editor": {
                        "id": "multiline",
                        "instructions": {
                            "en-GB": "Include a message to let an approver know your changes"
                        },
                        "properties": null
                    }
                }
            ]
        },
        {
            "id": "approve",
            "name": {
                "en-GB": "Approve"
            },
            "auditText": {
                "en-GB": "Approved"
            },
            "description": {
                "en-GB": "Approve the entry changes for publishing"
            },
            "transitionTo": "sysWorkflow",
            "color": "green",
            "groupId": "approveDecline",
            "uiAction": "navigateToEntryListing",
            "validate": false,
            "parameters": []
        }
    ],
    "color": "yellow",
    "uiEditorView": "previousPublishedVersionCompare",
    "allowUpdates": false
}
```