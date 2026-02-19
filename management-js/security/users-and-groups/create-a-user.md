1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Creates a new user resource from a [User](/help-and-docs/apis/management-js/model/user) object passed as an argument.

***create(user: User): Promise<User>***

## Remarks

Only a member of the *System Administrators* group can create a user resource.

## Example

JavaScript

```
let user = {    
    "userName": "tdurden",
    "email": "t.turden@fightclub.com",
    "firstname": "Tyler",
    "lastname": "Durden",
    "timezone": "America/New_York",
    "language": "en-US",
    "custom": {
        "department": "Soap sales"
    },
    "credentials": {
        "password": "pr0j3ctM4yh3m"
    }
};

client.security.users.create(user)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call fetch error: ', error);        
    });
```