1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)
5.  [Groups](/help-and-docs/apis/management-http/security/groups)

[Log in to add to favourites](/account/login)

Page last updated 17 June 2022

POST/api/security/groups/

## Responses

HTTP status code

Reason

Model

**201**

Created

[Group](/help-and-docs/apis/management-http/security/groups)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists in target location

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Create a group with custom data. This example also demonstrates all writeable fields of a group.

JSON

```
POST: /api/security/groups/
{
    "name": "Paper Street Soap Company",
    "Description": "Employees of the Paper Street Soap Company",
    "custom" : {
        "clientId": "PSSC"
    }
}
```

## Remarks

**Permissions**

Member of `System Administrators`.