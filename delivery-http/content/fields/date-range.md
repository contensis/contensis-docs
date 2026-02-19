## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Delivery API](/help-and-docs/apis/delivery-http)
4.  Content
5.  [Field](/help-and-docs/apis/delivery-http/content/fields)

[Log in to add to favourites](/account/login)

Page last updated 19 September 2024

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

Example

JSON

```
{
    "from": "2006-12-06T09:00:00",
    "to": "2009-09-10T09:00:00"
}
```