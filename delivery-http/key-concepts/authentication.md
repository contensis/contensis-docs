To access resources via the Delivery API, an Access Token is required with each request. This token is a read-only environment-specific credential that authorizes the retrieval of content from any project within that environment.

If you are a System Administrator, you can refer to [this](https://www.contensis.com/help-and-docs/guides/managing-your-environment/environment-access-token) guide to find your access token.

## Authorizing Requests

Once you have your environment access token, you can authenticate your API requests by including the token. The token can be passed as a query parameter (using the key accessToken) or in the request header (using the Authorization header).

Example HTTP request with an Authorization Header

HTTP

```
GET /api/delivery/projects/movieDb/entries/99aae243-ad6e-401b-89f9-90a51def6a18
Authorization: your-access-token-here
```

Example HTTP request with query parameters

HTTP

```
GET /api/delivery/projects/movieDb/entries/99aae243-ad6e-401b-89f9-90a51def6a18?accessToken=your-access-token-here
```