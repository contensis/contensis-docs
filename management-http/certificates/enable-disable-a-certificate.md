1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Certificates](/help-and-docs/apis/management-http/certificates)

[Log in to add to favourites](/account/login)

Page last updated 26 June 2024

PATCH/api/management/certificates/**{certificateId}**

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

[Certificate](/help-and-docs/apis/management-http/certificates)

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Certificate not found

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Enable a certificate

HTTP

```
PATCH: /api/management/certificates/fe1e4cad-bfb8-47b3-beea-c5e9d978f019
{
	"status": "enabled"
}
```

Disable a certificate

HTTP

```
PATCH: /api/management/certificates/fe1e4cad-bfb8-47b3-beea-c5e9d978f019
{
	"status": "disabled"
}
```

## Remarks

Disabling a certificate will immediatley remove the certificate from your site. If you want to avoid time without a certificate upload your new certificate first.