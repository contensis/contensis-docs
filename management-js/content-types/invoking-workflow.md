1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Content types

Workflow events can be invoked for a specific content type.

***invokeWorkflow(contentType: ContentType, event: string, data?: any): Promise<ContentType>***

## Parameters

Name

Type

Format

Description

contentType

object

[ContentType](https://www.contensis.com/help-and-docs/apis/management-js/model/content-type)

The content type object.

event

string

The event type, currently the only one supported for content types is *publish*.

data?

object

The optional event data.

## Returns

A Promise that will resolve with a [ContentType](https://www.contensis.com/help-and-docs/apis/management-js/model/content-type) object.

## Example

JavaScript

```
client.contentTypes.invokeWorkflow(existingContentType, 'publish')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```