1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

A group can be checked to see if it has a user member by using the following method:

***hasUser(groupId: string, userId: string): Promise<boolean>***

## Remarks

Membership will be classed as true if the user is a member of a child group of the specified group.

## Example

JavaScript

```
const groupId = "89CEE207-6F12-4D27-8693-B7693766A82D";
const userId = "F8B27A8F-F1E5-48EF-A5E6-19A791030C0A";
client.security.groups.hasUser(groupId, userId)
    .then(result => {
        console.log('API call result: ', result);        
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

---

A user can be checked to see if it is a member of a specific group or groups using the following method:

***userIsMemberOf(userId: string, …groupIdsOrNames: string\[\]): Promise<boolean>***

## Remarks

Membership will be classed as true if the user is a member of a child group of the specified group or groups.

## Examples

Single group

JavaScript

```
const userId = "0E2879B8-FA05-4291-BC99-035259B1CE61";
const groupId = "89CEE207-6F12-4D27-8693-B7693766A82D";
client.security.users.userIsMemberOf(userId, groupId)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

Multiple groups

JavaScript

```
const userId = "0E2879B8-FA05-4291-BC99-035259B1CE61";
const groupIds = ["89CEE207-6F12-4D27-8693-B7693766A82D", "2E86F729-9632-4D87-B38F-DF017F90B5CC"];
client.security.users.userIsMemberOf(userId, groupIds)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```