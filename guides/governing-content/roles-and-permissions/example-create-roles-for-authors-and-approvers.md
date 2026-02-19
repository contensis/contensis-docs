This article explains how to set up two basic roles to manage the process of publishing news content. By the end of this article you should understand the principles of setting up a role, assigning permissions, and adding users to a role.

We'll set up roles to support the following scenario:

-   Authors that can create news entries, but not publish or delete them.
-   The approvers are the only people on the team who can publish news content – they have to approve the content before it is published.

![](/image-library/resources-images/roles-example-content-type.x7944f67c.png?q=80&f=webp)

## Creating the roles

We'll start the process by creating the author role. Head over to the roles screen by selecting roles from the content types and entries drawer. If you don't see the roles option in the menu, you'll need to ask a system administrator to add you to the *Roles Administrator* group.

With the roles listing screen open, select **New role**. Enter the name for the role, in this example we'll use the name *News authors*. We'll provide an optional description to make clear what the role is for at a later date.

![](/image-library/resources-images/roles-example-new-role.xf777792d.png?q=80&f=webp)

With the role details populated, press **Create**. The roles builder will be displayed.

![](/image-library/resources-images/roles-add-permission.x5303651d.png?q=80&f=webp)

We can now begin the process of assigning the permissions for the role. Pressing **Add a permission** will add a new permission to the role and the permissions panel will be displayed.

Select the content type that you want to set permissions for from the dropdown list, in this example the *News* content type.

A list of events will be displayed following the selection of the content type. Permissions are explicitly set, by default permissions for events are switched off. Toggling the permission turns it on. For the author content type we'll enable the following permissions:

Create

Save

Submit / revoke

Approve / decline

Delete

✅ Yes

✅ Yes

✅ Yes

❌No

❌No

With the permissions now set up for the news authors, we'll press **Save** and begin to assign users who can carry out the actions assigned to the role.

![](/image-library/resources-images/roles-example-role-authors.x64d5f74e.png?q=80&f=webp)

Selecting the **Users and groups** tab will display two empty lists. One for users and the other groups. We'll type the name of a user for this example in the users search box to add to the role.

![](/image-library/resources-images/roles-example-role-authors-user.x9b15a80e.png?q=80&f=webp)

With the user assigned, and role permissions set we'll press **Save** and move on to creating the next role.

### The approver

The approver role has a completely different set of permissions, but the process is the same. In the case of an approver, we'll set the permissions of **Approve/decline** and **Delete**. The user that we assign to the role won't be able to create entries, save any changes, or submit the content for approval.

Create

Save

Submit / revoke

Approve / decline

Delete

❌No

❌No

❌No

✅ Yes

✅ Yes

## Testing the roles

Once the roles have been set up, you will have the following roles defined.

-   News author – can create, update and submit news entries.
-   News approver – can Approve/decline and delete news entries.

The Contensis interface will adapt to the permissions that are assigned to the role for the logged-in user.

The following screenshots provide a snapshot of how the interface will be displayed for the different users that have been assigned to the role.

### News author

#### Authors listing view

![](/image-library/resources-images/role-author-listing.xfcd2fc39.png?q=80&f=webp)

The entry listing screen above is displayed as it would be for a member of the *News authors* role. The new entry button is present, as well as the ability to edit all news entries.

#### Authors editor view

![](/image-library/resources-images/role-author-entry.xfef80d3c.png?q=80&f=webp)

The entry editor screen above is displayed as it would be for a member of the *News authors* role. The author can create the entry and submit it for approval. There is no *Delete* button available.

### News approver

#### Approvers listing view

![](/image-library/resources-images/role-approver-listing.x40cc7ce2.png?q=80&f=webp)

The entry listing screen above is displayed as it would be for a member of the *News approvers* role. The new entry button is not present and each entry can be opened in a read-only view.

#### Approvers editor view

![](/image-library/resources-images/role-approver-entry.x73bf6d1e.png?q=80&f=webp)

The entry editor above is displayed as it would be for a member of the *News approvers* role. The approvers can approve or decline the entry as well as see the entry's activity. They cannot edit the entry as fields are marked as read-only.

## Summary

We've created two roles that give different permissions to the same content type and separate the responsibility of producing news content.

These roles can easily be expanded to support additional content types or different permissions. When experimenting with these roles for the first time, we recommend assigning your own users to test the role and prevent any unauthorised access.

For a detailed breakdown of the stages for creating a role take a look at our [roles and permissions articles](https://www.contensis.com/help-and-docs/user-guides/governance/roles-and-permissions/roles-and-permissions-overview).