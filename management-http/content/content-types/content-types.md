Content types define structured content, broken down into smaller chunks or fields. For example, a **Film** content type might include fields like *Title*, *Film Poster*, *Runtime*, *Budget*, *Overview*, *Director*, and *Cast Members*. Each field provides specific information about the content.

You can create and customize content types using the **content type builder**. Each field within a content type is defined by:

-   **Name**: The label of the field
-   **Data type**: The type of data (e.g., string, number, etc.)
-   **Additional properties**: These may include validation rules, editor types, and content guidelines.

Find more information on [how to create and manage content types](/help-and-docs/guides/modelling-content/content-types/overview) in our user guides

### Supported data formats

Each content type has a **dataFormat** that specifies the type of content it generates. We currently support three data formats:

1.  **Entry**: Generates content entries
2.  **Asset**: Manages digital assets
3.  **Form**: Manages form responses

Each data format shares some common properties, but there are specific nuances for each type, which we will show below.

## Common properties for all data formats

Name

Type

Format

Description

**id**

string

uuid

A unique identifier for the content type or form

**projectId**

string

\-

The project identifier found in the project overview screen of the management console

**name**

string

localized value

The friendly name given to a content type or form

**description**

string

localized value

The description text given to a content type or form

**entryTitleField**

string

\-

The id of the field which should be used as the title in listings of entries or form responses

**entryDescriptionField**

string

\-

The id of the field which should be used as the description in listings of entries or form responses

**fields**

object\[...\]

field

A collection of fields that form the schema for an entry or form response

**groups**

object\[...\]

[content type group](/help-and-docs/apis/management-http/content/content-types/content-type-group)

A collection of groups that enable related fields to be grouped together in the UI

**enabled**

boolean

\-

If enabled then entries can be created from the content type, or form responses can be created from the form

**defaultLanguage**

string

language

The default language of entries created using the content type, or form responses created using the form

**supportedLanguages**

string\[...\]

language

A list languages which the content type or form supports

**workflowId**

string

\-

The workflow that derived entries or form responses will follow

**dataFormat**

string

\-

Either entry or asset for content types, or form for forms

**previewUrl**

string

\-

The URL where an example of an entry based on the content type, or a form response based on the form, can be viewed

**defaultRendererId**

string

uuid

The ID for the default renderer for the content type. Null if there is no default renderer. Currently used for content types only (not forms).

**defaultParentNodeId**

string

uuid

The ID for the default parent node for the content type. Null if there is no default parent node. All entries created using the content type will be created in the following node. Currently used for content types only (not forms).

**version**

object

version

Version information about the content type or form

## Entry & Asset content type specific properties

Name

Type

Format

Description

**previewUrl**

string

\-

URL where a preview of an entry based on the content type can be viewed

**defaultRendererId**

string

uuid

The ID for the default renderer, if applicable

**defaultParentNodeId**

string

uuid

The ID for the default parent node, if applicable

### Example content type for a movie entry

The content type "movie" includes fields such as title, tagline, overview, release date, and a list of associated actors, which are organised into two groups: "summary" and "additionalInfo," displayed as tabs when editing an entry. The title and overview fields are designated as the primary title and description fields. The content type supports four languages (en-GB, fr-FR, de-DE, es-ES) and uses the standard approval workflow (contensisEntryApproval). All entries created from this content type are stored in the folder with ID `a74c369c-203b-4828-bb0b-10cd65a1f63d`.

JSON

```
{
    "uuid": "ab4c6293-857e-4791-9b16-d146947f3016",
    "id": "movie",
    "projectId": "website",
    "name": {
        "en-GB": "Movie"
    },
    "description": {
        "en-GB": "A content type representing a movie, including essential details such as title, release date, and overview."
    },
    "entryTitleField": "title",
    "entryDescriptionField": "overview",
    "fields": [
        {
            "id": "title",
            "name": {
                "en-GB": "Movie Title"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {
                "en-GB": "The official title of the movie, suitable for display in various regions."
            },
            "default": null,
            "validations": {},
            "editor": {
                "id": "text",
                "instructions": {
                    "en-GB": "Provide the full official title of the movie."
                },
                "label": {},
                "properties": {
                    "placeholderText": {
                        "en-GB": "e.g., Inception, The Godfather"
                    }
                }
            },
            "groupId": "summary"
        },
        {
            "id": "tagline",
            "name": {
                "en-GB": "Movie Tagline"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {
                "en-GB": "A short, catchy tagline used to market the movie."
            },
            "default": null,
            "validations": {},
            "editor": {
                "id": "text",
                "instructions": {
                    "en-GB": "Enter the movie's promotional tagline, if available."
                },
                "label": {},
                "properties": {
                    "placeholderText": {
                        "en-GB": "e.g., \"In space, no one can hear you scream.\""
                    }
                }
            },
            "groupId": "summary"
        },
        {
            "id": "releaseDate",
            "name": {
                "en-GB": "Release Date"
            },
            "dataType": "dateTime",
            "dataFormat": null,
            "description": {
                "en-GB": "The date when the movie was or will be released."
            },
            "default": null,
            "validations": {},
            "editor": {
                "id": "date",
                "instructions": {
                    "en-GB": "Select the official release date of the movie."
                },
                "label": {},
                "properties": null
            },
            "groupId": "summary"
        },
        {
            "id": "overview",
            "name": {
                "en-GB": "Movie Overview"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {
                "en-GB": "A brief summary of the movie, providing an overview of the plot."
            },
            "default": null,
            "validations": {},
            "editor": {
                "id": "multiline",
                "instructions": {
                    "en-GB": "Write a concise summary that describes the movie's storyline, without revealing spoilers."
                },
                "label": {},
                "properties": null
            },
            "groupId": "additionalInfo"
        },
        {
            "id": "genre",
            "name": {
                "en-GB": "Movie Genre"
            },
            "dataType": "stringArray",
            "dataFormat": null,
            "description": {
                "en-GB": "The category or type of film based on its narrative style, target audience, or thematic content. Multiple genres can apply."
            },
            "default": null,
            "validations": {
                "minCount": {
                    "message": {
                        "en-GB": "Please select one or more genres that best describe the movie."
                    },
                    "value": 1
                },
                "allowedValues": {
                    "values": [
                        {
                            "en-GB": "Action"
                        },
                        {
                            "en-GB": "Comedy"
                        },
                        {
                            "en-GB": "Drama"
                        },
                        {
                            "en-GB": "Horror"
                        },
                        {
                            "en-GB": "Science fiction"
                        },
                        {
                            "en-GB": "Thriller"
                        }
                    ],
                    "labeledValues": [
                        {
                            "value": "action",
                            "label": {
                                "en-GB": "Action"
                            }
                        },
                        {
                            "value": "comedy",
                            "label": {
                                "en-GB": "Comedy"
                            }
                        },
                        {
                            "value": "drama",
                            "label": {
                                "en-GB": "Drama"
                            }
                        },
                        {
                            "value": "horror",
                            "label": {
                                "en-GB": "Horror"
                            }
                        },
                        {
                            "value": "science-fiction",
                            "label": {
                                "en-GB": "Science fiction"
                            }
                        },
                        {
                            "value": "thriller",
                            "label": {
                                "en-GB": "Thriller"
                            }
                        }
                    ],
                    "message": {
                        "en-GB": "Please select one or more genres that best describe the movie."
                    }
                }
            },
            "editor": {
                "id": null,
                "instructions": {
                    "en-GB": "Choose one or more genres that best categorise the movie."
                },
                "label": {},
                "properties": null
            },
            "groupId": "additionalInfo"
        }
    ],
    "defaultLanguage": "en-GB",
    "supportedLanguages": [
        "en-GB",
        "fr-FR",
        "de-DE",
        "es-ES"
    ],
    "workflowId": "contensisEntryApproval",
    "dataFormat": "entry",
    "previewUrl": "http://preview.mymoviewebsite.com/movies/{slug}",
    "defaultParentNodeId": "a74c369c-203b-4828-bb0b-10cd65a1f63d",
    "groups": [
        {
            "id": "summary",
            "name": {
                "en-GB": "Primary Movie Details"
            },
            "description": {
                "en-GB": "Contains the core information such as title, release date, and tagline."
            }
        },
        {
            "id": "additionalInfo",
            "name": {
                "en-GB": "Additional Movie Information"
            },
            "description": {
                "en-GB": "Holds supplementary data, including the movie's overview and other relevant details."
            }
        }
    ],
    "includeInDelivery": true,
    "enabled": true,
    "version": {
        "createdBy": "f.darabont",
        "created": "2024-09-19T08:05:41.1934535Z",
        "modifiedBy": "t.robbins",
        "modified": "2024-09-19T08:18:18.0774455Z",
        "publishedBy": "m.freeman",
        "published": "2024-09-19T08:15:58.2722109Z",
        "deletedBy": null,
        "deleted": null,
        "archivedBy": null,
        "archived": null,
        "versionNo": "2.1",
        "permanentDeletion": null
    }
}
```

## Form content type specific properties

Name

Type

Format

Description

**properties.autoCloseDateTime**

datetime

\-

Automatically close the form at a specific date and time

**properties.autoCloseForm**

boolean

\-

Enable automatic closing of the form

**properties.autoResponderRules**

object\[...\]

rule

Rules for auto-responders

**properties.autoSaveProgress**

boolean

\-

Enables the save form progress functionaility in the forms render package

**properties.captcha.enabled**

boolean

\-

Enable CAPTCHA for the form

**properties.confirmationRules**

object\[...\]

rule

Rules for form submission confirmation

**properties.retentionPeriodDays**

integer

\-

The retention period (in days) for form responses

**properties.localizations**

object

\-

Localization settings for the form

**properties.notificationRules**

object\[...\]

rule

Rules for form notifications

**properties.requirePermissionToPost**

boolean

\-

Restrict form submission to authorized users

### Example content type for an enquiry form

The content type "enquiryForm" includes fields such as name, mobile number, email address, type of enquiry, and a detailed enquiry description, which are organized into two groups: "Your details" and "Enquiry details," displayed as tabs when editing an entry. The content type supports one language (en-GB) and uses the "contensisFormBasic" workflow. Auto-responses and notifications are configured for specific enquiry types, such as FOI requests. All entries created from this content type are subject to a 40-day retention period and rendered with Captcha.

JSON

```
{
    "id": "enquiryForm",
    "projectId": "website",
    "name": {
        "en-GB": "Enquiry Form"
    },
    "description": {},
    "entryTitleField": "reference",
    "fields": [
        {
            "id": "name",
            "name": {
                "en-GB": "Name"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {},
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": {},
                "label": {
                    "en-GB": "Name"
                },
                "properties": {
                    "placeholderText": {
                        "en-GB": "Name placeholder"
                    }
                }
            },
            "groupId": "main"
        },
        {
            "id": "mobileNumber",
            "name": {
                "en-GB": "Mobile Number"
            },
            "dataType": "string",
            "dataFormat": "phone",
            "description": {},
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": {},
                "label": {
                    "en-GB": "Mobile Number"
                },
                "properties": null
            },
            "groupId": "main"
        },
        {
            "id": "emailAddress",
            "name": {
                "en-GB": "Email address"
            },
            "dataType": "string",
            "dataFormat": "email",
            "description": {},
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": {},
                "label": {
                    "en-GB": "Email address"
                },
                "properties": null
            },
            "groupId": "main"
        },
        {
            "id": "typeOfEnquiry",
            "name": {
                "en-GB": "Type of enquiry"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {},
            "default": null,
            "validations": {
                "allowedValues": {
                    "labeledValues": [
                        {
                            "value": "general-enquiry",
                            "label": {
                                "en-GB": "General enquiry"
                            }
                        },
                        {
                            "value": "complaint",
                            "label": {
                                "en-GB": "Complaint"
                            }
                        },
                        {
                            "value": "request-for-information",
                            "label": {
                                "en-GB": "Request for information"
                            }
                        }
                    ],
                    "message": null
                }
            },
            "editor": {
                "id": "list-dropdown",
                "instructions": {},
                "label": {
                    "en-GB": "Type of enquiry"
                },
                "properties": null
            },
            "groupId": "enquiryDetails"
        },
        {
            "id": "enquiry",
            "name": {
                "en-GB": "Enquiry"
            },
            "dataType": "string",
            "dataFormat": null,
            "description": {},
            "default": null,
            "validations": {},
            "editor": {
                "id": "multiline",
                "instructions": {},
                "label": {
                    "en-GB": "Enquiry"
                },
                "properties": {
                    "rows": 4
                }
            },
            "groupId": "enquiryDetails"
        },
        {
            "id": "reference",
            "name": {
                "en-GB": "Reference"
            },
            "dataType": "string",
            "dataFormat": "reference",
            "description": {},
            "default": null,
            "validations": {},
            "editor": {
                "id": null,
                "instructions": {},
                "label": {},
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
            "name": {
                "en-GB": "Your details"
            },
            "description": {}
        },
        {
            "id": "enquiryDetails",
            "name": {
                "en-GB": "Enquiry details"
            },
            "description": {}
        }
    ],
    "includeInDelivery": false,
    "enabled": true,
    "properties": {
        "autoResponderRules": [
            {
                "when": {
                    "and": [
                        {
                            "field": "typeOfEnquiry",
                            "equalTo": "request-for-information"
                        }
                    ]
                },
                "return": {
                    "email": {
                        "en-GB": {
                            "from": "foi-request@contensis.com",
                            "to": "{{emailAddress}}",
                            "subject": "We have received your FOI request",
                            "body": [
                                {
                                    "id": "4c404234",
                                    "type": "_paragraph",
                                    "value": "We have received your FOI request. We aim to respond to all FOI requests with 72 hours."
                                }
                            ]
                        }
                    }
                }
            }
        ],
        "captcha": {
            "enabled": false
        },
        "confirmationRules": [
            {
                "when": {
                    "and": [
                        {
                            "field": "typeOfEnquiry",
                            "equalTo": "request-for-information"
                        }
                    ]
                },
                "return": {
                    "content": {
                        "en-GB": [
                            {
                                "id": "35704e61",
                                "type": "_paragraph",
                                "value": "Thanks for your FOI request. We aim to respond to all FOI requests within 72 hours."
                            }
                        ]
                    }
                }
            },
            {
                "return": {
                    "content": {
                        "en-GB": [
                            {
                                "id": "8deda4a8",
                                "type": "_paragraph",
                                "value": "Thanks for your enquiry"
                            }
                        ]
                    }
                }
            }
        ],
        "retentionPeriodDays": 40,
        "localizations": {
            "errorSummaryTitle": {
                "en-GB": "There has been an error submitting the form, please try again"
            }
        },
        "notificationRules": [
            {
                "when": {
                    "and": [
                        {
                            "field": "typeOfEnquiry",
                            "equalTo": "request-for-information"
                        }
                    ]
                },
                "return": {
                    "email": {
                        "en-GB": {
                            "to": "foi-request@contensis.com",
                            "subject": "We have received an FOI request",
                            "body": [
                                {
                                    "id": "f00a6b95",
                                    "type": "_paragraph",
                                    "value": "We have received an FOI request, here are the details:"
                                },
                                {
                                    "id": "fc7795e4",
                                    "type": "_paragraph",
                                    "value": [
                                        {
                                            "id": "e6fd15a0",
                                            "type": "_fragment",
                                            "value": "Name: "
                                        },
                                        {
                                            "id": "9c5623a3",
                                            "type": "_liquid",
                                            "properties": {
                                                "type": "variable"
                                            },
                                            "value": "{{ name }}"
                                        }
                                    ]
                                }
                            ]
                        }
                    }
                }
            }
        ],
        "requirePermissionToPost": false
    },
    "version": {
        "createdBy": "e.parker",
        "created": "2024-07-04T17:12:10.9379449Z",
        "modifiedBy": "o.taylor",
        "modified": "2024-09-19T06:08:23.3136617Z",
        "publishedBy": "s.martinez",
        "published": "2024-09-19T06:08:24.7199347Z",
        "deletedBy": null,
        "deleted": null,
        "archivedBy": null,
        "archived": null,
        "versionNo": "1.0",
        "permanentDeletion": null
    }
}
```