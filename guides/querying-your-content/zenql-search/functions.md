1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Querying your content](/help-and-docs/guides/querying-your-content)
4.  ZENQL search

[Log in to add to favourites](/account/login)

Page last updated 22 July 2025

## On this page

-   [Date functions](#date-functions)
-   [Functions API support](#functions-api-support)

ZenQL provides a set of built-in functions that can be used in place of static values. These functions allow you to create dynamic searches without having to build complex queries, or where it simply wouldn't be possible without them.

## Date functions

Each date function generates a UTC date time value that is accurate to the millisecond. For example, the *startOfDay()* function starts from the first millisecond of the day. Date functions can be combined with [relative time periods](/help-and-docs/user-guides/zenql-search/zenql-search-relative-time-period) to provide a rich way of searching resources with minimal effort.

### currentUser()

Perform searches based on the currently authenticated user.

-   Where the owner of the entry is the current user.  
    `sys.owner = currentUser()`
-   Entries modified by the current user  
    `sys.version.modifiedBy = currentUser()`

### now()

Perform searches based on the current time (in UTC).

-   Release date greater than the current time.  
    `releaseDate > now()`
-   List all items that have been created in the last 4 days from the current time. For example, if now is Friday at 10:00am, then show results from Monday 10:00am onwards.  
    `sys.version.created >= now(-4d)`

### startOfDay()

Perform searches based on the start of the day.

-   List all items that have been updated since the start of the day.  
    `sys.version.modified >= startOfDay()`
-   Show me all items that were modified in the first 7 hours of the day.  
    `sys.version.modified >= startOfDay(7h)`

### endOfDay()

Perform searches based on the end of the day.

-   List all items that were created yesterday.  
    `sys.version.created <= endOfDay(-1d)`

### startOfWeek()

Perform searches based on the start of the week. The start of a week is based on a Monday.

-   List all items that were created since the start of the week.  
    `sys.version.created >= startOfWeek()`
-   Show all items that were modified before the start of the week.  
    `sys.version.modified < startOfWeek()`
-   Show all items that were created last week.  
    `sys.version.created >= startOfWeek(-1w)`
-   Offset the start of the week by a day, e.g. Sunday  
    `startOfWeek(-1d)`

### endOfWeek()

Perform searches based on the end of the week.

-   Show all items that were created last week *(week is inferred)*.  
    `sys.version.created <= endOfWeek(-1w)`

### startOfMonth()

Perform searches based on the start of the month.

-   List all items that have been created since the start of the month.  
    `sys.version.created >= startOfMonth()`
-   Show all items that have been created in the last year, including the current month.  
    `sys.version.created >= startOfMonth(-1y)`

### endOfMonth()

Perform searches based on the end of the month.

-   List all items that were created between the start and the end of the month.  
    `sys.version.created >= startOfMonth() and sys.version.created <= endOfMonth()`

### thisYear() - Coming

Perform searches based on the current year. A shortened version of `between(startOfYear(), endOfYear())`.

-   List all items that were created this year.  
    `sys.version.created thisYear()`
-   List all items that were modified last year *(year is inferred)*.  
    `sys.version.modified thisYear(-1)`

### startOfYear()

Perform searches based on the start of the year.

-   List all items that were created since the start of the year.  
    `sys.version.created >= startOfYear()`
-   Show all items that were modified last year.  
    `sys.version.modified < startOfYear(-1y)`

### endOfYear()

Perform searches based on the end of the year.

-   List all items that have been create this year.  
    `sys.version.created >= startOfYear() and sys.version.created <= endOfYear()`

### EMPTY

Perform a search to validate that field data is either `null` or contains an empty string. This funtion is helpful where you want to ensure your data is populated or not. This function is combined with an `IS` or `IS NOT` keyword.

-   Check for blank alt text of an image field called photo.  
    `photo.altText IS EMPTY`
-   Images with a caption on a field called photo.  
    `photo.cpation IS NOT EMPTY`

### Relative period

Perform searches based on a time period. [Relative periods](http://preview.contensis.zenhub.contensis.cloud/help-and-docs/user-guides/zenql-search/zenql-search-relative-time-period) can be combined by ensuring they are wrapped in double quotes.

-   Modified in the last 30 days.  
    `sys.version.modified > -30d`
-   Modified a week and 2 days ago.  
    `sys.version.modified > -1w 2d`

## Functions API support

**Function**

**Entries**

**Users & groups**

now()

✅

✅

startOfDay()

✅

✅

endOfDay()

✅

✅

startOfWeek()

✅

✅

endOfWeek()

✅

✅

startOfMonth()

✅

✅

endOfMonth()

✅

✅

startOfYear()

✅

✅

endOfYear()

✅

✅

Relative period

✅

✅

## On this page

-   [Date functions](#date-functions)
-   [Functions API support](#functions-api-support)