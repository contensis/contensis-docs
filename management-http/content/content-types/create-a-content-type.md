JSON

```
{
    "id": "movie",
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
    ]
}
```