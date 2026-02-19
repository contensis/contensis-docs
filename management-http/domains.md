## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)

[Log in to add to favourites](/account/login)

Page last updated 07 April 2025

## Properties

Name

Type

Format

Description

Example

**id**

string

GUID

The domain identifier as a 128 bit GUID.

**hostHeader**

string

\-

The host header of the domain

www.mysite.com

**isPrimary**

boolean

\-

If set to \`true\` then this domain will be used as the primary domain for your live site. Only one domain can be set as a primary domain for a given project

**version**

object

version

The version information for the domain

## Example

JSON

```
{
	"id": "20fc2914-86da-4767-b21f-4df1e5d378c4",
	"hostHeader": "www.mysite.com",
	"isPrimary": true,
	"version": {
		"created": "2024-06-18T15:11:41.556962",
		"createdBy": "ca68b801-4688-44b3-b5ed-fe4cdb29cb06",
		"modified": "2024-06-19T16:00:25.276619",
		"modifiedBy": "73c7770d-f6c8-4cd1-9024-2667a9c91e42"
	}
}
```