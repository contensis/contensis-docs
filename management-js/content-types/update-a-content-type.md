JavaScript

```
existingContentType.description['en-GB'] = 'A movie content type';

client.contentTypes.update(existingContentType)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
  });
```