1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Gets the direct child group members of the group.

***getChildGroupsByGroupId(groupId: string): Promise<PagedList<Group>>***

## Example

JavaScript

```
let groupId = "4b262379-5bbe-421e-a429-f6e2ab5a849b";

client.security.groups.getChildGroupsByGroupId(groupId)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

---

Gets the direct child group members of the group.

***getChildGroupsByGroupName(groupName: string): Promise<PagedList<Group>>***

## Example

JavaScript

```
let groupName = "Test Users";

client.security.groups.getChildGroupsByGroupName(groupName)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```