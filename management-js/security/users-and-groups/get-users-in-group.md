1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Gets the users as direct members of the group.

***getUsersByGroupId(groupId: string): Promise<PagedList<User>>***

## Example

JavaScript

```
let groupId = "4b262379-5bbe-421e-a429-f6e2ab5a849b";

client.security.groups.getUsersByGroupId(groupId)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

---

Gets the users as direct members of the group.

***getUsersByGroupName(groupName: string): Promise<PagedList<User>>***

## Example

JavaScript

```
let groupName = "Test Users";

client.security.groups.getUsersByGroupName(groupName)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```