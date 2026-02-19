1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

A user can be added to a group by using the following method:

***addUser(groupId: string, userId: string): Promise<void>***

## Example

JavaScript

```
const groupId = "89CEE207-6F12-4D27-8693-B7693766A82D";
const userId = "F8B27A8F-F1E5-48EF-A5E6-19A791030C0A";
client.security.groups.addUser(groupId, userId)
    .then(result => {
        console.log('API call was successful');              
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

---

Multiple users can be added to a group by using the following method:

***addUsers(groupId: string, userIds: string\[\]): Promise<void>***

## Example

JavaScript

```
const groupId = "89CEE207-6F12-4D27-8693-B7693766A82D";
const userIds = [
    "75490b0f-56f7-4690-a20a-6f2a822f1d3f",
    "20b5e923-beb8-44ab-8bb4-34467582230f",
    "13f8cd48-7765-47b7-9fa3-2ad9c935a4be",
    "3c3d98a1-c80a-49d1-b602-f38ad2b01af8",
    "11f5ce76-ca86-45d8-9928-d7fd56863ec7"
];

client.security.groups.addUsers(groupId, userIds)
    .then(result => {
        console.log('API call was successful');        
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```