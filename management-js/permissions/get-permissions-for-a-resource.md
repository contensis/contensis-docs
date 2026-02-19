1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Permissions

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

## Get permissions for a resource

Gets a permission set for the requested user and resource. Requesting a permission set returns the positive permission values assigned to the user for all roles the user is assigned to (either directly or via a group).

GET /api/management/projects/**{projectId}**/security/permissions/**{resourceType}**/**{resourceId?}**?userId=**{userId}**&language=**{language}**

### Parameters

Name

Parameter type

Type

Format

Description

projectId

path

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

resourceType

path

string

The type of resource to retrieve permissions for. Contenttypes or entries.

resourceId

path

GUID

Optional id of the resource to retrieve permissions for.

userId

query

string

The id of the user to retrieve permissions for.

language

query

string

[LanguageCode](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/localization)

The optional language code to retrieve permissions for.

### Example request

HTTP

```
GET: /api/management/projects/movieDb/security/permissions/entries/a65a9d9d-ee64-4c25-a80c-ab5aee00fb9d?userId=a.user
```

### Response message

HTTP status code

Reason

Response model

200

Success

Array of actions available

404

NotFound

[Error](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/errors)

500

InternalServerError

[Error](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/errors)

### Example response

JSON

```
{
    "actions": ["sysCreate", "draft.sysDelete", "draft.submit", "draft.sysUpdate", "submitted.revoke"]
}
```

### Validations

#### Project does not exist

Roles are project specific. If you attempt to get a role in a project which does not exist you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors getting the role",
    "data": [
        {
            "field": "projectId",
            "message": "The project does not exist"
        }
    ],
    "type": "Validation"
}
```