Creates a new content type resource from a [ContentType](https://www.contensis.com/help-and-docs/apis/management-js/model/content-type) object passed as an argument.

***create(contentType: ContentType): Promise<ContentType>***

JavaScript

```
let newContentType = {
    "id": "movie",
    "projectId": "movieDb",
    "name": {
        "en-GB": "Movie"
    },
    "description": {
        "en-GB": "A movie type"
    },
    "entryTitleField": "title",
    "entryDescriptionField": "overview",
    "fields": [
        {
            "id": "title",
            "name": {
                "en-GB": "Title"
            },
            "dataType": "string",
            "editor": {
                "id": "text",
                "instructions": {
                    "en-GB": "The title of the movie"
                },
                "properties": {
                    "placeholderText": {
                        "en-GB": "Enter the full title of the movie appropriate to the region"
                    }
                }
            }
        },
        {
            "id": "tagline",
            "name": {
                "en-GB": "Tagline"
            },
            "dataType": "string",
        },
        {
            "id": "overview",
            "name": {
                "en-GB": "Overview"
            },
            "dataType": "string",
            "dataFormat": "html"
        },
        {
            "id": "releaseDate",
            "name": {
                "en-GB": "Release Date"
            },
            "dataType": "dateTime",
            "validations": null
        },
        {
            "id": "actors",
            "name": {
                "en-GB": "Actors"
            },
            "dataType": "objectArray",
            "dataFormat": "entry",
            "validations": {
                "contentType": {
                    "contentType": "actor"
                }
            }
        }
    ],
    "defaultLanguage": "en-GB",
    "supportedLanguages": [
        "en-GB",
        "fr-FR",
        "de-DE",
        "es"
    ],
    "workflowId": "ContensisMultilingual",
    "dataFormat": "entry"
};

client.contentTypes.create(newContentType)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
  });
```

Type

Description

Project does not exist

A project must exist to be able to create content types.

Non-unique id

The content type must be unique for the project.

If the *defaultLanguage* value is not included in the *supportedLanguages* array then it will automatically be added by the service when the project is created. Additionally, if the *defaultLanguage* is not specified then the [Project](https://www.contensis.com/help-and-docs/apis/management-js/model/project) *primaryLanguage* will be automatically set as the value by the service.