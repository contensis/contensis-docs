1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

## List users

User resources can be retrieved as a paged list by passing an optional [UserListOptions](/help-and-docs/apis/management-js/model/user-list-options) object as an argument.

***list(options?: UserListOptions): Promise<PagedList<User>>***

## Returns

A Promise that will resolve with a [PagedList](/help-and-docs/apis/management-js/model/paged-list) that contains an array of [User](/help-and-docs/apis/management-js/model/user) objects.

## Example

JavaScript

```
client.security.users.list({
        q: 'mycompany.com',
        pageOptions: { pageIndex: 1, pageSize: 5 },
        order: ['userName']
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call error: ', error);      
});
```