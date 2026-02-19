## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

## Properties

Name

Type

Format

Description

Example

**id**

string

\-

The block identifier. It must begin with a letter and only contain lowercase alphanumeric characters and hyphen separators

movie-listing

**description**

string

\-

The description of the block

**liveVersion**

number

integer

The version number of the last version made live

**madeLive**

datetime

datetime

The last time the block was made live

**versionsSinceLive**

number

integer

A count of versions created since the block was last made live

**projectId**

string

\-

The project identifier found in the project overview screen of the management console

movieDb

**branches**

object\[...\]

\-

An array of branches which are available for the block

**branches.id**

string

\-

The name of the branch

main

## Example

JSON

```
[
	{
		"id": "movie-listing",
		"description": "Displays the main listing for movies on the movie example site",
		"liveVersion": 4,
		"versionsSinceLive": 2,
		"madeLive": "2021-03-02T11:16:01.408Z",
		"projectId": "movieDb",
		"branches": [
			{
				"id": "main"
			}
		]
	}
]
```