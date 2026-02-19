1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Components

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

Gets the components for a project.

***list(versionStatus?: VersionStatus): Promise<Component\[\]>***

## Returns

A Promise that will resolve with an array of [Component](/help-and-docs/apis/management-js/model/component) objects.

## Parameters

Name

Type

Description

versionStatus

string

The version status, either *published* or *latest*. The default is *latest*.

## Example

JavaScript

```
client.components.list('published')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```