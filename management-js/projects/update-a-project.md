1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Projects

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

## Update a project

Updates an existing project resource.

***update(project: Project): Promise<Project>***

### Returns

A Promise that will resolve with a [Project](/help-and-docs/apis/management-js/model/project) object.

### Example

JavaScript

```
client.projects.update({
    "description": "A source of movie and TV series in multiple languages",    
    "supportedLanguage": [
        "fr-FR",
        "de-DE",
        "en-US"
    ]
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

### Remarks

It is not possible to update the Id once you've created a project.