1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 19 September 2024

There are three system defined permissions that can be assigned, these are:

Permission

Description

sysCreate

If a role is assigned this permission users in the role are then able to create entries of the given content type(s)

sysDelete

If a role is assigned this permission users in the role are then able to delete entries for the given content type(s) and states

sysUpdate

If a role is assigned this permission users in the role are then able to update entries for the given content type(s) and states

The create permission is set at the workflow level, all other permissions are set against a given state.

The remaining permissions are based on the workflow that has been assigned, given a work flow is assigned with a state called awaitingApproval which has the following events; approve, decline and revoke. Then there will be three additional permissions which can be assigned; awaitingApproval.approve, awaitingApproval.decline, awaitingApproval.sysUpdate and awaitingApproval.revoke.

If a user has permission for events in a given workflow state they will be able to invoke those events.