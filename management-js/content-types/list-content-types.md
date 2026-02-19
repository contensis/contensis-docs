1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Content types

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Gets the content types for a project by passing an optional [ContentTypeListOptions](/help-and-docs/apis/management-js/model/content-type-list-options) object as an argument.

***list(options?: ContentTypeListOptions): Promise<ContentType\[\]>***

## Returns

A Promise that will resolve with an array of [ContentType](/help-and-docs/apis/management-js/model/content-type) objects.

## Example

JavaScript

```
client.contentTypes.list({    
    versionStatus: 'published',
    dataFormat: 'entry'
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```