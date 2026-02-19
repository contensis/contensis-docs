1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 09 March 2022

A user can update their password with a call that includes a new password and the user's current password in a parameter defined in [UserUpdatePasswordOptions](https://www.contensis.com/help-and-docs/apis/management-js/model/user-update-password-options).  
A member of the *System Administrators* group can update the password without the need to provide the existing password.

***updatePassword(options: UserUpdatePasswordOptions): Promise<void>***

## Remarks

If the existing password is wrong then an exception with a *409 Conflict status* is thrown.  
If the new password does not meet the password policy then an exception with a *422 Unprocessable Entity* status is thrown.

## Example for a non-admin user

JavaScript

```
let options = {    
    "userId": "4b262379-5bbe-421e-a429-f6e2ab5a849b",
    "existing": "m4rl451ng3r",
    "new": "pr0j3ctM4yh3m"
};

client.security.users.updatePassword(options)
    .then( result => {
        console.log('API call was successful');
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

## Example for a System Adminstrators user

JavaScript

```
let options = {    
    "userId": "4b262379-5bbe-421e-a429-f6e2ab5a849b",    
    "new": "pr0j3ctM4yh3m"
};

client.security.users.updatePassword(options)
    .then( result => {
        console.log('API call was successful');
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```