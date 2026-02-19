1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Projects

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Deletes a project resource.

***delete(id: string): Promise<void>***

### Returns

A Promise that will resolve with an empty object.

## Example

JavaScript

```
client.projects.delete('website')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

### Validations

#### Single project

A project cannot be deleted if it is the only project in a Contensis instance. If you attempt to delete all projects in a Contensis instance, you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors deleting the project 'movieDb'",
    "data": [
        {
            "field": "",
            "message": "The specified project is the only project and therefore cannot be deleted"
        }
    ],
    "type": "Validation"
}
```

#### A project containing content

In order to delete a project it has to be empty. This is a safeguard to stop people deleting projects which are in use. If you attempt to delete a project which contains content types, you will get the following response.

JSON

```
{
    "logId": "5fca7986-5ba3-4eb4-9cea-b5f25aaaed09",
    "message": "There are validation errors deleting the project 'movieDb'",
    "data": [
        {
            "field": "",
            "message": "The project has associated content types so cannot be deleted"
        }
    ],
    "type": "Validation"
}
```