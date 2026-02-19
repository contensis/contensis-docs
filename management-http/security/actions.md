1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 05 December 2025

Actions can be POST'ed to a resource's actions endpoint to perform a modification on the resource.

## Available actions

Users:

-   suspend
-   unsuspend
-   unlock
-   forcePasswordReset
-   setPasswordToExpirable

## Example requests

Suspend a user

HTTP

```
POST: /api/security/users/82f73a9b-2a13-4d63-bcc1-e8ee5047b01c/actions/
{
    "type": "suspend"
}
```

### Still need help?

If you still need help after reading this article, don't hesitate to reach out to the [Contensis community on Slack](https://app.slack.com/client/T5MSMUE3H/C5MSMUYHM) or raise a support ticket to get help from our team.

[New support request](https://www.contensis.com/support)