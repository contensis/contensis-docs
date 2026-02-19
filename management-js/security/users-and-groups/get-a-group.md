1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

## Get a group by id

A group resource can be retrieved by it's GUID identifier.

***getById(groupId: string): Promise<Group>***

## Returns

A Promise that will resolve with a [Group](https://www.contensis.com/help-and-docs/apis/management-js/model/group) object.

## Example

JavaScript

```
client.security.groups.getById('bd8f92eb-d137-49d8-9e7a-560078a8a530')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call error: ', error);      
});
```

---

A group resource can be retrieved by its name.

***getByName(username: string): Promise<Group>***

## Example

JavaScript

```
client.security.groups.getByNme('Test Group')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call error: ', error);      
});
```