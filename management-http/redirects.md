## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)

[Log in to add to favourites](/account/login)

Page last updated 04 July 2024

## Properties

Name

Type

Format

Description

Example

**id**

string

GUID

The unique identifier of the redirect as a 128 bit GUID

**sourceDomain**

string

URI

This specifies the domain from which the redirect should apply. If you want the redirect applied to all available domains then specify \*

**destination**

string

\-

The URL or path you want to redirect to, either relative or a fully qualified URL e.g. https://www.my-new-site.com or /new-address/news

**statusCode**

integer

\-

This is the HTTP status code to be used for the redirect. Current supported status codes are 301: Moved Permanently and 302: Found

301

**appendSourcePathToDestination**

boolean

\-

This boolean property indicates whether the path of the source URL should be appended to the destination URL. If false, only the base destination URL is used.

**match**

object

\-

Container for match details

**match.type**

string

\-

Specifies the type of match to be performed. Possible values are beginsWith, exactMatch and regex.

**match.value**

string

\-

The specific string or pattern that the source URL must match. If a regex is being used then it must be in PCRE format

**version**

object

version

The version information for the redirect

## Example

JSON

```
{
	"id": "aab967ef-d2cf-43bb-96a4-c943b118c6f7",
	"sourceDomain": "example.com",
	"destination": "/new-path",
	"statusCode": 301,
	"appendSourcePathToDestination": false,
	"match": {
		"type": "beginsWith",
		"value": "/old-path"
	},
	"version": {
		"created": "2023-05-04T12:05:42.376971",
		"createdBy": "3376a167-3e97-407f-981b-600aecec0401",
		"modified": "2023-05-04T12:05:42.376975",
		"modifiedBy": "3376a167-3e97-407f-981b-600aecec0401"
	}
}
```