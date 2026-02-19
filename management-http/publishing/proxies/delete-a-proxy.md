1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  proxies

[Log in to add to favourites](/account/login)

Page last updated 17 January 2023

DELETE/api/management/projects/**{projectId}**/proxies/**{proxyId}**

## Parameters

Name

Parameter type

Type

Format

Description

**projectId***(required)*

path

string

\-

The project identifier found in the project overview screen of the management console.

**proxyId***(required)*

path

string

guid

The proxy identifier

## Responses

HTTP status code

Reason

Model

**204**

Success

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Delete a proxy with id ec0b25dc-0c46-4a90-8610-c0886c51b709

HTTP

```
DELETE: /api/management/projects/website/proxies/ec0b25dc-0c46-4a90-8610-c0886c51b709
```