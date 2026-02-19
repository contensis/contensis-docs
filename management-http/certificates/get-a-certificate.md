1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Certificates](https://www.contensis.com/help-and-docs/apis/management-http/certificates)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 26 June 2024

GET/api/management/certificates/**{certificateId}**

## Parameter

Name

Parameter type

Type

Format

Description

**certificateId***(required)*

path

string

guid

The certificate identifier

## Responses

HTTP status code

Reason

Model

**200**

Success

[Certificate](https://www.contensis.com/help-and-docs/apis/management-http/certificates)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Certificate not found

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

HTTP

```
GET: /api/management/certificates/3a74d859-d028-4c7c-a9c7-823a8b2e4a3b

	{
		"id": "3a74d859-d028-4c7c-a9c7-823a8b2e4a3b",
		"status": "enabled",
		"commonName": "secure.site.com",
		"keySize": 2048,
		"issuer": "Secure Certs Inc.",
		"public": "-----BEGIN CERTIFICATE-----...-----END CERTIFICATE-----",
		"issued": "2022-10-10T12:00:00",
		"sans": ["secure.site.com", "www.secure.site.com"],
		"expiry": "2024-10-10T12:00:00",
		"version": {
			"created": "2023-03-01T09:30:45.123456",
			"createdBy": "user1"
		}
	}
```