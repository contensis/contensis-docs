1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

The date range object represents a start and end point in time.

## Properties

Name

Type

Format

Description

from

datetime

The date and time the range starts

to

datetime

The date and time the range ends

## Validation

The *from* value cannot be greater than the *to* value.

## Example

JSON

```
{
    "from": "2006-12-06T09:00:00",
    "to": "2009-09-10T09:00:00"
}
```