1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Querying your content](https://www.contensis.com/help-and-docs/guides/querying-your-content)
4.  ZENQL search

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 20 June 2025

## On this page

-   [DateTime](#datetime)
-   [String](#string)
-   [Numeric](#numeric)
-   [Boolean](#boolean)
-   [UUIDs](#uuids)

ZenQL supports the following data types. These data types are represented in the JSON response of our resources and are documented here for reference.

## DateTime

Dates and time are stored as UTC for all our resources. However, you can provide ZenQL with a variety of date and time formats to make searches easier.

Date/time formats support by ZenQL

**Format**

**Example**

yyyy-MM-ddTHH:mm:ss.sTZD (ISO standard)

1997-07-09T19:20:30.45+01:00

yyyy-MM-dd

1997-07-09

yyyy-MM-dd HH:mm

1997-07-09 19:20

yyyy-MM-dd HH:mm:ss

1997-07-09 19:20:30

yyyy/MM/dd

1997/07/09

yyyy/MM/dd HH:mm

1997/07/09 19:20

yyyy/MM/dd HH:mm:ss

1997/07/09 19:20:30

Time Period

\-5d, 4w 2d, see [Relative time period](https://cms-zenhub.cloud.contensis.com/help-and-docs/user-guides/zenql-search/zenql-search-relative-time-period)

All of the above formats are also valid in single month and/or single day formats, for example, 1997-7-9 (yyyy-M-d) or 1997/7/9 (yyyy/M/d).

Dates and time periods do not need to be wrapped in quotes, for example:

sys.version.modified > 2020-03-01

sys.version.modified > 2020-03-01 12:00:00

sys.version.published > 5d

## String

String searches are not case sensitive, for example:

`sys.contentTypeId = plant` is the same as `sys.contentTypeId = Plant`

Multi-word phrases should be wrapped in double quotes.

description ~ "your home"

## Numeric

Integers or decimals do not need to be wrapped in double quotes.

`height > 10.0` or `height < 10`

## Boolean

Boolean values are also expressed without double quotes.

`displayOnHomepage = true` or `displayOnHomepage = false`

## UUIDs

ZenQL intrinsically understands a UUID of a resource and does not need to be wrapped in quotes.

`sys.id = 3695fac7-bbe4-4637-894a-8857bc662638`

## On this page

-   [DateTime](#datetime)
-   [String](#string)
-   [Numeric](#numeric)
-   [Boolean](#boolean)
-   [UUIDs](#uuids)