1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Components

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Components are added to a content type as a field just like any other field, however the dataFormat of the field specifies the id of the component to add.

For example if you have a component with an id of "movieRole" then the dataFormat value would be "component.movieRole".

## Example

JavaScript

```
existingContentType.fields.push({  
    "id":"movieRole",
    "name": {  
        "en-GB":"Movie Role"
    },
    "dataType":"object",
    "dataFormat":"component.movieRole",
    "description": {  
        "en-GB":"The movie Role"
    }
});

client.contentTypes.update(existingContentType)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
  });
```

After a content type has been saved with a component field, all of the component's fields are added to a nested fields collection within the component field on the content type. A components' fields are read-only, and cannot be modified from the content type.