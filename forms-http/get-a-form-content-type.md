JSON

```
{
    "id": "enquiryForm",
    "projectId": "website",
    "name": "Enquiry Form",
    "description": null,
    "entryTitleField": "reference",
    "fields": [
        {
            "id": "name",
            "name": "Name",
            "dataType": "string",
            "dataFormat": null,
            "description": null,
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": null,
                "label": "Name",
                "properties": {
                    "placeholderText": "Name placeholder"
                }
            },
            "groupId": "main"
        },
        {
            "id": "mobileNumber",
            "name": "Mobile Number",
            "dataType": "string",
            "dataFormat": "phone",
            "description": null,
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": null,
                "label": "Mobile Number",
                "properties": {}
            },
            "groupId": "main"
        },
        {
            "id": "emailAddress",
            "name": "Email address",
            "dataType": "string",
            "dataFormat": "email",
            "description": null,
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": null,
                "label": "Email address",
                "properties": {}
            },
            "groupId": "main"
        },
        {
            "id": "typeOfEnquiry",
            "name": "Type of enquiry",
            "dataType": "string",
            "dataFormat": null,
            "description": null,
            "default": null,
            "validations": {
                "allowedValues": {
                    "labeledValues": [
                        {
                            "value": "general-enquiry",
                            "label": "General enquiry"
                        },
                        {
                            "value": "complaint",
                            "label": "Complaint"
                        },
                        {
                            "value": "request-for-information",
                            "label": "Request for information"
                        }
                    ],
                    "message": null
                }
            },
            "editor": {
                "id": "list-dropdown",
                "instructions": null,
                "label": "Type of enquiry",
                "properties": {}
            },
            "groupId": "enquiryDetails"
        },
        {
            "id": "enquiry",
            "name": "Enquiry",
            "dataType": "string",
            "dataFormat": null,
            "description": null,
            "default": null,
            "validations": {},
            "editor": {
                "id": "multiline",
                "instructions": null,
                "label": "Enquiry",
                "properties": {
                    "rows": 4
                }
            },
            "groupId": "enquiryDetails"
        },
        {
            "id": "reference",
            "name": "Reference",
            "dataType": "string",
            "dataFormat": "reference",
            "description": null,
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": null,
                "label": null,
                "properties": {
                    "prefix": "EF"
                }
            },
            "groupId": "main"
        }
    ],
    "defaultLanguage": "en-GB",
    "supportedLanguages": [
        "en-GB"
    ],
    "workflowId": "contensisFormBasic",
    "dataFormat": "form",
    "groups": [
        {
            "id": "main",
            "name": "Your details",
            "description": null
        },
        {
            "id": "enquiryDetails",
            "name": "Enquiry details",
            "description": null
        }
    ],
    "includeInDelivery": false,
    "enabled": true,
    "properties": {
        "autoCloseForm": true,
        "autoCloseDateTime": "2045-11-02T00:00:00",
        "autoSaveProgress": true,
        "captcha": {
            "enabled": true
        },
        "localizations": {
            "errorSummaryTitle": "There has been an error submitting the form, please try again.",
            "closedReasonMessage": "We are no longer accepting enquiries"
        }
    },
    "language": "en-GB",
    "version": {
        "versionNo": "17.0"
    }
}
```