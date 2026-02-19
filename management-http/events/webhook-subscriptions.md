JSON

```
{
    "id": "3a7ce8e3-9c9f-4242-be20-35edb29c4a07",
    "name": "name",
    "description": "some description",
    // Urls can be templated
    "url": "https://external.mywebsite.com/handlewebhooks/{/resource/sys.id}",
    "enabled": true,
    "method": "POST",
    "topics": [
        {
            "resourceType": "entry",
            "event": ["updated", "created"],
            "language": ["fr-fr"],
            "contentTypeId": ["blog", "news"],
            "owner": "t.durden"
        },
        {
            "resourceType": "entry",
            "event": ["published"],
            "contentTypeId": ["news"],
            "owner": "t.durden"
        },
        {
            "resourceType": "contentType",
            "event": ["created"]
        },
        {
            "resourceType": "entry",
            "event": ["workflowEventRaised"],
            "contentTypeId": ["blog"],
            "owner": "t.durden",
            "workflowEvent" : ["contensisentrybasic.draft.submit", "contensisentryapproval.awaitingApproval.approve"]
        },
        {
            "resourceType": "entry",
            "event": ["workflowEventRaised"],
            "contentTypeId": ["news"],
            "owner": "t.durden",
            "workflowEvent" : ["contensisentryapproval.awaitingApproval.declined"]
        },
        {
            "resourceType": "entry",
            "event": ["workflowStateChanged"],
            "contentTypeId": ["blog"],
            "owner": "t.durden",
            "workflowState" : ["contensisentryapproval.awaitingApproval"]
        }
    ],
    "headers": {
        "target": {
            "value": "internal"
        },
 
 
        // Headers can be templated
        "department": {
            "value": "{/resource/department}"
        },
 
        // Headers can be specified as secret, which means that the value can be set but won't be returned
 
        // Set
        "secretHeaderSet": {
            "secret": true,
            "value": "cs7vdsdvj~8"
        },
 
        // Get
        "secretHeaderGet": {
			"value": "************",
            "secret": true
        }
 
        // NOTE: A header will not be returned if it has no value
    },
    "templates": {
 
        // For entry events return a custom structure with specific pieces of data
        "entry": "{\n\"event\": \"{/event/name}\",\n\"user\": \"{/user/firstName} {/user/lastName}\",\n\"id\": \"{/resource/sys/id}\",\n\"title\": \"{/resource/entryTitle}\",\n\"description\": \"{/resource/entryDescription}\",\n\"department\": \"{/resource/department}\"}",
 
 
        // A news specific template
        "entry.news": "{\n\"event\": \"{/event/name}\",\n\"id\": \"{/resource/sys/id}\",\n\"title\": \"{/resource/entryTitle}\",\n\"headline\": \"{/resource/headline}\"}",
 
        // For content type events return the entire content type resource (root)
        "contentType": "{/resource/}"
 
        // For all other events if a template for a resource is not supplied then return the default webhook request structure
    },
    "version": {
        "createdBy": "t.durden",
        "created": "2020-09-01T08:59:49Z",
        "modifiedBy": "m.singer",
        "modified": "2020-09-05T08:59:49Z",
        "versionNo": "1.0"
    }
}
```