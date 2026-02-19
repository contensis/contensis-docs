1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Creates a new group resource from a [Group](/help-and-docs/apis/management-js/model/group) object passed as an argument.

***create(group: Group): Promise<Group>***

## Remarks

Only a member of the *System Administrators* group can create a group resource.

## Example

JavaScript

```
let group = {    
    "name": "Paper Street Soap Company",
    "Description": "Employees of the Paper Street Soap Company", 
    "type": "contensis",
    "custom" : {
        "clientId": "PSSC"
    }
};

client.security.groups.create(group)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call fetch error: ', error);        
    });
```