1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Roles

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

## List roles

Role resources can be retrieved as a paged list by passing an optional [PageOptions](https://www.contensis.com/help-and-docs/apis/management-js/model/page-options) object as an argument.

***list(options?: PageOptions): Promise<PagedList<Role>>***

## Returns

A Promise that will resolve with a [PagedList](https://www.contensis.com/help-and-docs/apis/management-js/model/paged-list) that contains an array of [Role](https://www.contensis.com/help-and-docs/apis/management-js/model/role) objects.

## Example

JavaScript

```
client.roles.list({
        pageIndex: 1, 
        pageSize: 5
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call error: ', error);      
});
```

### Validations

#### Project does not exist

Roles are project specific. If you attempt to list roles in a project which does not exist you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors listing the roles",
    "data": [
        {
            "field": "projectId",
            "message": "The project does not exist"
        }
    ],
    "type": "Validation"
}
```

#### Insufficient permissions to list roles

In order to list roles you must be a member of the "System Administrators" user group. If you do not have permission to list roles you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors listing the roles",
    "data": [
        {
            "message": "Access denied"
        }
    ],
    "type": "Validation"
}
```