1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  [Search basics](https://www.contensis.com/help-and-docs/apis/delivery-http/search-basics)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 24 September 2024

A Relative Time Period is a token that the Delivery API can convert to a date-time value relative to the current UTC date-time. It can be used stand-alone as an operand in search queries or passed as a parameter to any of the date-time [Expression Functions](https://www.contensis.com/help-and-docs/apis/delivery-http/search-basics/expression-functions). Used outside of an Expression Function now() is implied. That is, "-1d" is equivalent to "now(-1d)".

### Syntax

The token consists of 1 or more space-delimited segments and can optionally contain a preceding plus or minus sign. Thus the syntax is:

<token>:=

\[- | +\]<segment>\[ <segement> ...n\]

<segment>:=

<int>y|M|w|d|h|m

Used stand-alone to list records created in the last 24 hours.

JSON

```
{
    "pageIndex": 0,
    "pageSize": 25,
    "where": [
        {
            "field": "sys.version.created",
            "greaterThanOrEqualTo": "-1d"
        }
    ]
}
```

Used stand-alone to list records created since the start of the last week of the previous month.

JSON

```
{
    "pageIndex": 0,
    "pageSize": 25,
    "where": [
        {
            "field": "sys.version.created",
            "greaterThanOrEqualTo": "-1M 1w"
        }
    ]
}
```

Used as a parameter to an Expression Function to list records created last year.

JSON

```
{
    "pageIndex": 0,
    "pageSize": 25,
    "where": [
        {
            "field": "sys.version.created",
            "greaterThanOrEqualTo": "startOfYear(-1)"
        },
        {
            "field": "sys.version.created",
            "lessThanOrEqualTo": "endOfYear(-1)"
        }
    ]
}
```