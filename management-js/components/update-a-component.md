JavaScript

```
existingComponent.description['en-GB'] = 'UK address component';

client.components.update(existingComponent)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
  });
```