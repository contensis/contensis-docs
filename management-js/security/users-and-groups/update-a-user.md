1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Updated a user resource from a [User](/help-and-docs/apis/management-js/model/user) object passed as an argument.

***update(user: User): Promise<User>***

## Remarks

Only the current user and a member of the *System Administrators* group can update a user resource

## Example

JavaScript

```
let user = {    
    "userId": "4b262379-5bbe-421e-a429-f6e2ab5a849b",
    "email": "t.turden@test.com",    
    "custom": {
        "department": "Marketing"
    }    
};

client.security.users.update(user)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```