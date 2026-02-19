1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Deletes a node by id.

***delete(id: string): Promise<void>***

### Example

JavaScript

```
client.nodes.delete('c31111e7-76f7-46dd-93fb-cbf81a853a37')
  .then(result => {      
    console.log('API call was successful');              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```