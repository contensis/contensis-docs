1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Entries

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Lists entries by content type id or by passing an [EntryListOptions](/help-and-docs/apis/management-js/model/entry-list-options) object as an argument.

***list(contentTypeIdOrOptions: string | EntryListOptions): Promise<PagedList<Entry>>***

## Returns

A Promise that will resolve with a [PagedList](/help-and-docs/apis/management-js/model/paged-list) that contains an array of [Entry](/help-and-docs/apis/management-js/model/entry) objects.

## Example

JavaScript

```
client.entries.list({    
    contentTypeId: 'movie',
    versionStatus: 'published',
    language: 'fr-FR',
    order: ['entryTitle'],
    pageOptions: {      
      pageSize: 50
    }    
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```