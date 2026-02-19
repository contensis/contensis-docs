1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Security

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

## Bearer token

On a successful authentication response the *access\_token* value must be set as the Authorization HTTP header for all REST requests and must be formatted as follows:

HTTP

```
Authorization: bearer {access_token}
```

Periodically the access token will expire to ensure that if compromised, then any grants are short lived. This expiry can be forecast by using the *expires\_in* value returned from an authentication response or can be handled by catching a `401 - Unauthorized` response.

401 - Unauthorized

JSON

```
{
  "message": "Authorization has been denied for this request."
}
```

On an expiry a new access token will need to be requested using the same mechanism as the initial token request.

**Note** - If you want to implement your own Delivery API wrapper, then it must implement the [OAuth 2.0 client credential flow](https://tools.ietf.org/html/rfc6749#section-4.4) using the discovery document located at `https://*YOUR_CMS_URL*/authenticate`.