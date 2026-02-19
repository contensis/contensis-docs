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