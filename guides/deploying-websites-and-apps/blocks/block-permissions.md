## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Deploying websites and apps](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps)
4.  Blocks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 28 May 2024

Blocks are permissioned using roles and support the following actions.

Action

Description

Push

Allows your CI/CD build to push a Block to Contensis.

Release

Allows members of a role to mark a Block as being released and ready for production.

Make live / rollback

Allows members of a role to make a Block live to production.

Start / Stop

Allows members of a role to start and stop a Block manually.

Mark as broken

Allows members of a role to mark a Block as broken and to take the Block offline.

Delete

Allows members of a role to delete a Block.

View

Allows members of a role to see Blocks but not make any changes.

## Role example: Blocks CI

You will generally have a role configured for your CI/CD pipeline to carry out actions during the CI build process.

Action

Description

Push

Allows your CI/CD build to push a Block to Contensis.

Release

Allows the Block to be auto-released after a successful CI build.

## Role example: Blocks administrator

A Blocks Administrator role will generally have all actions applied, allowing the user to manage Blocks without any restrictions.