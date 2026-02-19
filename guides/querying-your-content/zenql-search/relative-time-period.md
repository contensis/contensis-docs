1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Querying your content](https://www.contensis.com/help-and-docs/guides/querying-your-content)
4.  ZENQL search

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 29 May 2024

A relative time period is a token that can convert a date and time value, relative to the current date and time (UTC). It can be used in an operator or as a parameter of a [date time function](https://www.contensis.com/help-and-docs/user-guides/zenql-search/zenql-search-functions).

## Syntax

The token consists of 1 or more space-delimited segments and can optionally contain a preceding plus or minus sign. The sign can only be used once and is applied to the whole expression. When combining segments, there is no need enclose them in double quotes.

<token>:=  
    \[- | +\]<segment>\[ <segment> ...n\]

<segment>:=  
    <int>y|M|w|d|h|m

Supported relative periods

**Period**

**Syntax**

**Example**

Year

{int}y

1y

Month

{int}M

2M

Week

{int}w

2w

Day

{int}d

5d

Hour

{int}h

10h

Minute

{int}m

15m

## Examples

-   Show all items that have been created in the last 24 hours.  
    `sys.version.created >= -1d`
-   Used stand-alone to list records created in the last month plus 1 week.  
    `sys.version.created >= -1M 1w`
-   Used as a parameter to an Expression Function to list records created last year. *The year is inferred by the [date function](https://www.contensis.com/help-and-docs/user-guides/zenql-search/zenql-search-functions)*.  
    `sys.version.created >= startOfYear(-1) and <= endOfYear(-1)`