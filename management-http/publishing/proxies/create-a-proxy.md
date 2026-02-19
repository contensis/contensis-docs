1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  proxies

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

POST/api/management/projects/**{projectId}**/proxies

## Parameter

Name

Parameter type

Type

Description

**projectId***(required)*

path

string

The project identifier found in the project overview screen of the management console.

## Responses

HTTP status code

Reason

Model

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Create a new proxy for a specific project

JSON

```
Accept: application/json
POST: /api/management/projects/website/proxies

{
    "id": "7622b5f7-e245-4226-9e64-3aeafa930eae",
    "projectId": "movieDb",
    "name": "Thrillers section",
    "description": "Proxies current website thrillers section",
    "endpoints": {
        "*": {
            "server": "10.65.18.4",
            "ssl": true,
            "headers": {
                "host": "www.moviedb-oldsite.com"
            }
        },
        "fr-FR": {
            "server": "10.65.18.4",
            "ssl": true,
            "headers": {
                "host": "www.moviedb.fr"
            }
        }
    },
    "version": {
        "versionNo": "2.0",
        "created": "2020-02-13T10:15:12.1973648+01:00",
        "createdBy": "t.durden",
        "modified": "2020-02-13T10:15:12.1973648+01:00",
        "modifiedBy": "t.durden",
        "published": "2020-02-13T10:15:12.1973648+01:00",
        "publishedBy": "t.durden"
    }
}
```