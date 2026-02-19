1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Updated a group resource from a [Group](https://www.contensis.com/help-and-docs/apis/management-js/model/group) object passed as an argument.

***update(group: Group): Promise<Group>***

## Remarks

Only a member of the *System Administrators* group can update a group resource.

## Example

JavaScript

```
let group = {    
    "id": "4b262379-5bbe-421e-a429-f6e2ab5a849b",
    "name": "Paper Street Soap Company",
    "Description": "Employees of the Paper Street Soap Company", 
    "type": "contensis",
    "custom" : {
        "clientId": "PSSC"
    }
};

client.security.groups.update(group)
    .then(result => {
        console.log('API call result: ', result);
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```