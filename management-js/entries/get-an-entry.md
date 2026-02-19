1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Entries

[Log in to add to favourites](/account/login)

Page last updated 26 May 2021

An entry definition in the Management API contains a mixture of standard properties and properties that have been defined by the content type that an [entry](/help-and-docs/user-guides/authoring/entries "Entries") is based on.

## Get an entry

Gets an existing entry by its id or by passing an [EntryGetOptions](/help-and-docs/apis/management-js/model/entry-get-options) object as an argument.

***get(idOrOptions: string | EntryGetOptions): Promise<Entry>***

### Returns

A Promise that will resolve with an [Entry](/help-and-docs/apis/management-js/model/entry) object.

### Example

JavaScript

```
client.entries.get('bd8f92eb-d137-49d8-9e7a-560078a8a530')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});

client.entries.get({
    id: 'bd8f92eb-d137-49d8-9e7a-560078a8a530',
    versionStatus: 'published'
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});

client.entries.get({
    id: 'bd8f92eb-d137-49d8-9e7a-560078a8a530',
    version: '1.2',
    language: 'fr-FR'
  })
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```