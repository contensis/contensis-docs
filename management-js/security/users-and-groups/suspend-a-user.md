1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

A user can be suspended using the following call:

***suspendUser(userId: string): Promise<void>***

## Remarks

The *userId* can be username, email address or a GUID identifier.

If the user is not found then an exception with a *404 Not found* is thrown.  
If there are no permissions to suspend a user then an exception with a *403 Forbidden* status is thrown.

## Example

JavaScript

```
client.security.users.suspendUser("4b262379-5bbe-421e-a429-f6e2ab5a849b")
    .then( result => {
        console.log('API call was successful');
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```