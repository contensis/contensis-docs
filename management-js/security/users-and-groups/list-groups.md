1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

## List groups

Group resources can be retrieved as a paged list by passing an optional [GroupListOptions](https://www.contensis.com/help-and-docs/apis/management-js/model/group-list-options) object as an argument.

***list(options?: GroupListOptions): Promise<PagedList<Group>>***

## Returns

A Promise that will resolve with a [PagedList](https://www.contensis.com/help-and-docs/apis/management-js/model/paged-list) that contains an array of [Group](https://www.contensis.com/help-and-docs/apis/management-js/model/group) objects.

## Example

JavaScript

```
client.security.groups.list({
        q: 'Administrators',
        pageOptions: { pageIndex: 1, pageSize: 5 },
        order: ['name']
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call error: ', error);      
});
```