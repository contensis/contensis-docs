1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security
5.  Users and groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

Deletes a group by its id.

***delete(id: string): Promise<void>***

## Remarks

Only a member of the *System Administrators* group can delete a group resource.

JavaScript

```
let groupId = "4b262379-5bbe-421e-a429-f6e2ab5a849b";

client.security.groups.delete(groupId)
    .then(result => {
        console.log('API call was successful');
    })
    .catch(error => {
        console.log('API call error: ', error);        
    });
```

### Still need help?

If you still need help after reading this article, don't hesitate to reach out to the [Contensis community on Slack](https://app.slack.com/client/T5MSMUE3H/C5MSMUYHM) or raise a support ticket to get help from our team.

[New support request](https://www.contensis.com/support)