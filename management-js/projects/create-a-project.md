1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Projects

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

## Create a project

Creates a new project resource from a [Project](/help-and-docs/apis/management-js/model/project) object passed as an argument.

***create(project: Project): Promise<Project>***

### Returns

A Promise that will resolve with a [Project](/help-and-docs/apis/management-js/model/project) object.

### Example

JavaScript

```
client.projects.create({
    "id": "movieDb",
    "name": "Movie database",
    "description": "A source of movie and TV series",
    "primaryLanguage": "en-GB",
    "supportedLanguage": [
        "fr-FR",
        "de-DE"
    ]
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

### Validations

#### Non-unique id

A project must have a unique id. If you attempt to create a project with an id which is already in use you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors creating the project",
    "data": [
        {
            "field": "",
            "message": "A project with this Id already exists"
        }
    ],
    "type": "Validation"
}
```

#### Primary language is required

A project must have a primary language defined. If you attempt to create a project without specifying a primary language you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors creating the project",
    "data": [
        {
            "field": "Project",
            "message": "The primary language code is not valid"
        }
    ],
    "type": "Validation"
}
```

### Remarks

If the *primaryLanguage* value is not included in the *supportedLanguages* array then it will automatically be added by the service when the project is created.