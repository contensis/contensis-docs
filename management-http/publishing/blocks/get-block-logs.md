1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  publishing
5.  Blocks

[Log in to add to favourites](/account/login)

Page last updated 01 October 2021

GET/api/management/projects/**{projectId}**/blocks/**{blockId}**/**{branchId}**/versions/**{version}**/logs?dataCenter=hq

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

**blockId***(required)*

path

string

\-

The block identifier

**branchId***(required)*

path

string

\-

The branch identifier

**version***(required)*

path

string

\-

A label of either live or latest, or a valid version number.

**dataCenter***(required)*

query

string

\-

The name of the data center to view block logs in

**includeTimestamps**

query

boolean

\-

Whether or not to include system timestamps in block logs

**previous**

query

boolean

\-

Whether or not to show the last terminated container's logs

**lines**

query

number

integer

The number of log lines to return

**sinceSeconds**

query

number

integer

Return logs since the specified number of seconds

## Responses

HTTP status code

Reason

Model

**200**

Success

**401**

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

Get the container logs of a block

HTTP

```
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/5/logs?dataCenter=manchester
```

Get logs occurred since the last 10 seconds

HTTP

```
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/5/logs?dataCenter=manchester&since=10
```

Include timestamps in the logs

HTTP

```
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/5/logs?dataCenter=manchester&includeTimestamps=true
```

Return the last 500 log lines

HTTP

```
GET: /api/management/projects/movieDb/blocks/movielisting/main/versions/5/logs?dataCenter=london&lines=500
```