A user can be removed from a group by using the following method:

***removeUser(groupId: string, userId: string): Promise<void>***

JavaScript

```
const groupId = "89CEE207-6F12-4D27-8693-B7693766A82D";
const userId = "F8B27A8F-F1E5-48EF-A5E6-19A791030C0A";
client.security.groups.removeUser(groupId, userId)
    .then(result => {
        console.log('API call was successful');              
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```