All properties of the user resource object are optional **apart from the id**.

Any value provided for expiry must be a future date.  To clear an expiry date set the expiry property to null.

As shown in the example, a special header value of 'application/merge-patch+json; charset=utf-8' is required for the Content-Type http header.

**Permissions**

Members of `System Administrators` are permitted to patch any user.

Authenticated standard user accounts are permitted to patch their own user.