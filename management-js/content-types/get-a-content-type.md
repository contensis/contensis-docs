1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Content types

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

## Get a content type

Gets an existing content type by the content type id or by passing a [ContentTypeGetOptions](/help-and-docs/apis/management-js/model/content-type-get-options) object as an argument.

***get(idOrOptions: string | ContentTypeGetOptions): Promise<ContentType>***

### Returns

A Promise that will resolve with a [ContentType](/help-and-docs/apis/management-js/model/content-type) object.

### Example

JavaScript

```
client.contentTypes.get('movie')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});

client.contentTypes.get({
    id: 'movie',
    versionStatus: 'published'
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});

client.contentTypes.get({
    id: 'movie',
    version: '1.2'
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```