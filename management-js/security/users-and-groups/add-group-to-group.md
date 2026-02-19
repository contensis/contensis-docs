1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

A child group can be added to a group by using the following method:

***addChildGroup(groupId: string, childGroupId: string): Promise<void>***

## Remarks

A group cannot be added as a child group of itself.

## Example

JavaScript

```
const groupId = "89CEE207-6F12-4D27-8693-B7693766A82D";
const childGroupId = "F8B27A8F-F1E5-48EF-A5E6-19A791030C0A";
client.security.groups.addChildGroup(groupId, childGroupId)
    .then(result => {
        console.log('API call was successful');              
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```