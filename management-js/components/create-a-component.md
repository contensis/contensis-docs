1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Components

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Creates a new component resource from a [Component](/help-and-docs/apis/management-js/model/component) object passed as an argument.

***create(component: Component): Promise<Component>***

## Returns

A Promise that will resolve with a [Component](/help-and-docs/apis/management-js/model/component) object.

## Example

JavaScript

```
let newComponent = {
    "id": "address",
    "projectId": "movieDb",
    "name": {
        "en-GB": "Address"
    },
    "description": {
        "en-GB": "An address component"
    },    
    "fields": [
        {
            "id": "firstLine",
            "name": {
                "en-GB": "First line"
            },
            "dataType": "string",
            "editor": {
                "id": "text",
                "instructions": {
                    "en-GB": "The first line of address"
                },
                "properties": {
                    "placeholderText": {
                        "en-GB": "Enter the first line of address"
                    }
                }
            }
        },
        {
            "id": "postCode",
            "name": {
                "en-GB": "Post code"
            },
            "dataType": "string",
        }
    ]
};

client.components.create(newComponent)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
  });
```

## Validations

Type

Description

Project does not exist

A project must exist to be able to create components.

Non-unique id

The component must be unique for the project.