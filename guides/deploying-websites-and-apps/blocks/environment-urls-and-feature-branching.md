1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Deploying websites and apps](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps)
4.  Blocks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 28 May 2024

## Environment URLs

Each Contensis site will have the following URLs to be used as part of your development workflow.

The descriptions below outline the default behaviour of your site URLs before you make any changes using the preview toolbar.

Type

Description

URLs

Preview

The preview URL will use live Blocks and display the latest version of your entry content.

**Default project:** https://preview-{alias}.cloud.contensis.com **Additional projects:  
**https://preview-{projectApiId}-{alias}.cloud.contensis.com

Staging

The staging URL will use the latest released Blocks and display published entry content.

**Default project:** https://staging-{alias}.cloud.contensis.com **Additional projects:  
**https://staging-{projectApiId}-{alias}.cloud.contensis.com

Live (production)

The live URL will use live Blocks and display published entry content.

**Default project:** https://live-{alias}.cloud.contensis.com **Additional projects:  
**https://live-{projectApiId}-{alias}.cloud.contensis.com

## Git branching

Blocks also support Git branching, giving you more granular control of feature development. You can surface any number of feature branches in Contensis through your CI/CD pipeline configuration, essentially pushing a Block for each branch.

Each branch is indicated in the dropdown of the main page header of the *Block versions* screen.

Whilst you can have an unlimited number of feature branches in Git and Contensis, we only run 4 deployments for the branches with the latest activity. If a new branch is required, the branch with the least recent activity is stopped.

Branches with no activity for 30 days are stopped and marked as stale.