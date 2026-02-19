1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Nodes

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Creates a new child node under a specified parent node.

***create(node: Node): Promise<Node>***

### Returns

A Promise that will resolve with a [Node](/help-and-docs/apis/management-js/model/node) object.

### Example

JavaScript

```
let node = {
    "parentId": '7840f70a-b842-42ea-bfac-148a3b772ac8',
    "displayName": {
      "en-GB": "Tiger Escaped From Zoo",
      "fr-FR": "Tigre échappé du zoo"
    },
    "slug": {
      "en-GB": "tiger-escaped-from-zoo",
      "fr-FR": "tigre-s-est-echappe-du-zoo"
    },
    "restrictedToLanguages": [
      "en-GB",
      "fr-FR"
    ],
    "entryId": '273b8bfa-5dfe-409b-872d-95e6a72f6bc9',    
    "includeInMenu": true
};
client.nodes.create(node)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

## Minimum request

A node can be created by specifying only the title and the parent node:

JavaScript

```
let node = {
    "parentId": '7840f70a-b842-42ea-bfac-148a3b772ac8',
    "displayName": {
        "en-GB": "Tiger Escaped From Zoo"
    }
};
client.nodes.create(node)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

## Validations

### Parent id

A node must have a parent id. If you attempt to create a node without a parent id you will get the following response:

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There were validation errors creating the node",
    "data": [
        {
            "field": "",
            "message": "The parent id cannot be an empty guid"
        }
    ],
    "type": "Validation"
}
```

### Parent child limit

A parent node cannot have more than 2000 children. If you attempt to create a node which breaches this limit you will get the following response:

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There were validation errors creating the node",
    "data": [
        {
            "field": "",
            "message": "A parent must not have more than 2000 children"
        }
    ],
    "type": "Validation"
}
```

### Depth limit

The maximum depth of a node is 10 levels. If you attempt to create a node which breaches this limit you will get the following response:

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There were validation errors creating the node",
    "data": [
        {
            "field": "",
            "message": "The maximum depth for a node is 10 levels deep"
        }
    ],
    "type": "Validation"
}
```

### Slug

A node must have at least one slug for a language. If you attempt to create a node without a slug you will get the following response:

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There were validation errors creating the node",
    "data": [
        {
            "field": "",
            "message": "A slug is required for at least one language"
        }
    ],
    "type": "Validation"
}
```

A node slug cannot be longer than 50 characters. If you attempt to create a node with a slug which breaches this you will get the following response:

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There were validation errors creating the node",
    "data": [
        {
            "field": "",
            "message": "The node slug cannot be longer than 50 characters"
        }
    ],
    "type": "Validation"
}
```

A node slug must be unique for a language on a given parent node. If you attempt to create a node which breaks this rule you will get the following response:

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There were validation errors creating the node",
    "data": [
        {
            "field": "",
            "message": "The node slug repeatedSlug exists for the language en-GB in parent f3322e4f-72b5-4064-be88-fcfed6c82635 in the tree 1126b642-409b-4372-bb17-0bdb7f641a5d"
        }
    ],
    "type": "Validation"
}
```