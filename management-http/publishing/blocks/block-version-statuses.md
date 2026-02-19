## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

A block version has a number of statuses

## Workflow status

Name

Description

Created

The block has just been pushed and has not yet started being discovered

Discovering

The block discovery process is ongoing

DiscoveryFailure

The block discovery process has failed

Draft

The block discovery process was successful and the block is now a draft version

Released

The block has been released and its major version incremented

## Deployment Status

These statuses describe the deployment status that has been specified for a block.

Name

Description

None

The block is not ready

Deployed

The block is intended to be run

Live

The block has been marked as live and publicly available

Deprecated

The block has been replaced with a newer version

## Running status

These statuses describe the current running status of the block.

Name

Description

None

The block has not been set to run

Pending

The block is intended to run and is currently being setup to do so

Starting

The block is currently starting up

Available

The block is running successfully

Stopped

The block was running but is no longer

Degraded

The block is not running successfully in one or more instances

Faulted

The block is not running successfully in all instances