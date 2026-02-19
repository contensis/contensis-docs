1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Roles

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

## Create a Role

Creates a new role.

***create(role: Role): Promise<Role>***

### Returns

A Promise that will resolve with a [Role](/help-and-docs/apis/management-js/model/role) object.

### Example

JavaScript

```
let role = {
    "name": {
        "en-GB": "Movie Editors"
    },
    "description": {
        "en-GB": "Movie editors can edit movies, but not submit or approve them"
    },
    "enabled": true,
    "permissions": {
        "entries": [
            {
                "id": "movie",
                "languages": ["en-GB"],
                "actions": ["sys.update", "awaitingApproval.revoke"]
            }
        ],
        "contentTypes": []
    },
    "assignments": {
        "users": ["a.user"],
        "groups": ["Movie Editors"],
        "apiKeys": ["Movie Import"]
    }
};
client.roles.create(role)
  .then(result => {      
    console.log('API call result: ', result);              
  })
  .catch(error => {
    console.log('API call fetch error: ', error);      
});
```

### Validations

#### Project does not exist

Roles are project specific. If you attempt to create a role in a project which does not exist you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors creating the role",
    "data": [
        {
            "field": "projectId",
            "message": "The project does not exist"
        }
    ],
    "type": "Validation"
}
```

#### Insufficient permissions to create a role

In order to create a role you must be a member of the "System Administrators" user group. If you do not have permission to create a role you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors creating the role",
    "data": [
        {
            "message": "Access denied"
        }
    ],
    "type": "Validation"
}
```

#### Content type does not exist

The content type must exist to be able to create a role. If you attempt to create a role for a content type which does not exist you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors creating the role",
    "data": [
        {
            "field": "entries[index].id",
            "message": "The content type 'movie' does not exist"
        }
    ],
    "type": "Validation"
}
```

#### Language unsupported by the content type

Language assignments for a content type id must be supported by the content type. If you attempt to create a role with a language which is not supported by the content type you will get the following response.

JSON

```
{
    "logId": "00000000-0000-0000-0000-000000000000",
    "message": "There are validation errors creating the role",
    "data": [
        {
            "field": "Role.Permissions.Entries[index]",
            "message": "The languages 'cy', 'fr' specified in the role are not supported by the content type."
        }
    ],
    "type": "Validation"
}
```