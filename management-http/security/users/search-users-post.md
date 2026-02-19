1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 August 2024

POST/api/security/users/search

## Responses

HTTP status code

Reason

Model

**200**

Success

[User](https://www.contensis.com/help-and-docs/apis/management-http/security/users)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get the first page of 50 users that contain the word tyler in the username or email, ordered by created date descending

HTTP

```
POST: /api/security/users/search

{
    "pageIndex": 0,
    "pageSize": 50,
    "where": [
        {
            "or": [
                {
                    "field": "username",
                    "contains": "tyler"
                },
                {
                    "field": "Email",
                    "contains": "tyler"
                }
            ]
        }
    ],
    "orderBy": [
        {
            "desc": "created"
        }
    ]
}
```

## Remarks

**Permissions**

Member of `System Administrators`.