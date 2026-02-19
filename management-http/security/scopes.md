## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)

[Log in to add to favourites](/account/login)

Page last updated 24 September 2024

OAuth 2.0 scopes allow a developer to specify which resources their application can access. These are included as a space-separated list value, in the scope parameter when invoking an [authentication](/help-and-docs/apis/management-http/security/authentication) request.

Scope name

Associated methods

Project\_Read

[Get a project](/help-and-docs/apis/management-http/projects/get-a-project)

Entry\_Read

[Get an entry](/help-and-docs/apis/management-http/content/entries/get-an-entry)  
[List entries](/help-and-docs/apis/management-http/content/entries/list-all-entries)  
[List entries by content type](/help-and-docs/apis/management-http/content/entries/list-entries-by-content-type)

Entry\_Write

[Create an entry](/help-and-docs/apis/management-http/content/entries/create-an-entry)  
[Update an entry](/help-and-docs/apis/management-http/content/entries/update-an-entry)  
[Publish an entry](/help-and-docs/apis/management-http/content/entries/invoking-workflow)

Entry\_Delete

[Delete an entry](/help-and-docs/apis/management-http/content/entries/delete-an-entry)

HTTP

```
POST: https://cms-yourcontensis.com/authenticate/connect/token
Content-Type: application/x-www-form-urlencoded
Accept: application/json

grant_type=client_credentials&
client_id=bda30e56-4faf-412c-b460-6fce9342b162&
client_secret=1e2759cee76b4ae7947722be71cc33e1-56a63ae1361241fdab7c9ee90cc8a6b3-6dc4c02b8eda43d49de499ad5eef1160&
scope=Entry_Read ContentType_Read Project_Read
```