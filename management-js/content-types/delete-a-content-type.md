1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Content types

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Deletes a content type from a specific project.

***delete(id: string): Promise<void>***

## Returns

A Promise that will resolve with an empty object.

## Example

JavaScript

```
client.contentTypes.delete('movie')
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

### Still need help?

If you still need help after reading this article, don't hesitate to reach out to the [Contensis community on Slack](https://app.slack.com/client/T5MSMUE3H/C5MSMUYHM) or raise a support ticket to get help from our team.

[New support request](https://www.contensis.com/support)