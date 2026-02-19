1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Gets the groups the user is a member of by passing the user id or a [UserGroupsOptions](https://www.contensis.com/help-and-docs/apis/management-js/model/user-group-options) object as an argument.

***getUserGroupsuserIdOrOptions: string | UserGroupsOptions): Promise<PagedList<Group>>***

## Example for direct parent groups

JavaScript

```
let userId = "4b262379-5bbe-421e-a429-f6e2ab5a849b";

client.security.users.getUserGroups(userId)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

## Example for inherited parent groups

JavaScript

```
let options = {
    userId: "4b262379-5bbe-421e-a429-f6e2ab5a849b",
    includeInherited: true
};

client.security.users.getUserGroups(options)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```