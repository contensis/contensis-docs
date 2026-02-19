1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Nodes

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Get all the children of a specific node by specifying the node id or a [NodeGetChildrenOptions](https://www.contensis.com/help-and-docs/apis/management-js/model/node-get-children-options) object.

***getChildren(idOrOptions: string | NodeGetChildrenOptions): Promise<Node\[\]>***

### Example

JavaScript

```
client.nodes.getChildren('c31111e7-76f7-46dd-93fb-cbf81a853a37')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});

client.nodes.getChildren({ id: 'c31111e7-76f7-46dd-93fb-cbf81a853a37',  language: 'fr-FR' })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```