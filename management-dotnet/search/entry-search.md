1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Search

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 09 December 2024

A query tree structure, along with order and paging specifiers, allows a search to be performed against indexed documents held in ElasticSearch. The query API allows any required sub-query structure to be defined and a comprehensive selection of Operators enable individual field level evaluation.

## Queries

This example demonstrates a simple search with default ordering and paging options:

### Synchronous

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;
using Zengenti.Search;

var client = ManagementClient.Create();
var websiteProject = client.Projects.Get("website");

var query = new Query(
    Op.Contains("title", "Batman"),
    Op.GreaterThan("runtime", 200)
);

// Execute the search returning entries
PagedList<Entry> entriesResult = websiteProject.Entries.Search(query);
```

### Asynchronous

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;
using Zengenti.Search;

var client = ManagementClient.Create();
var websiteProject = client.Projects.Get("website");

// Execute the search asynchronously returning entries
PagedList<Entry> entriesResult = await websiteProject.Entries.SearchAsync(query);
```

## Sub-queries

A sub-query is a query within another query that is used as a condition to further restrict the results. Effectively they are defined by an explicit nesting of [logical operators](https://www.contensis.com/help-and-docs/apis/management-dotnet/search/query-operators).

This example demonstrates a simple search with a sub-query:

C#

```
var query = new Query(
    Op.Contains("title", "Batman"),
    Op.Or(
        Op.GreaterThan("releaseDate", 1960),
        Op.Contains("tagline", "gotham")
    )
);
```

## Location searches

Search for locations within a radius of a specified location.

### Supported distance units

Unit

Search value

Mile

`mi` or `miles`

Yard

`yd` or `yards`

Feet

`ft` or `feet`

Inch

`in` or `inch`

Kilometer

`km` or `kilometers`

Meter

`m` or `meters`

Centimeter

`cm` or `centimeters`

Millimeter

`mm` or `millimeters`

Nautical mile

`NM`, `nmi` or `nauticalmiles`

### Example

Find all entries which have a location within 10.5 miles of Ludlow Castle's location.  
Append the search value at the end of the distance specified, so for example "10.5mi" or "10.5miles".

C#

```
var query = new Query(
    Op.DistanceWithin("location", 52.36700505, -2.72304296, "10.5mi"))
);
```

## Ordering

Results can be ordered by one or more fields in an ascending or descending direction. Order clauses are prioritised in the order that they are added. By default, if no order clauses are specified then the entry results are ordered by the EntryTitle in an ascending direction.

Order by 'releaseDate'.

C#

```
query.OrderBy.Add("releaseDate")
```

Order by 'releaseDate' in a descending direction using the '-' token.

C#

```
query.OrderBy.Add("-releaseDate")
```

Multiple order clauses.

C#

```
query.OrderBy.Add("title");
query.OrderBy.Add("-releaseDate");
```

## Paging

Paging allows the number of results to be restricted to a defined count so that the results are easier to handle and ensures a response is returned quickly. The page index can also be specified to allow which set of results is to be returned. The page size is limited to a maximum of 10,000 however this is not recommended.

C#

```
// Create a query
var query = new Query(
    Op.EqualTo("sys.contentTypeId", "film"));

// Set the number of entries to be returned per page
query.PageSize = 50;

// Get the 2nd result set
query.PageIndex = 1;
```

## Complete example

The example below combines the ordering and paging concepts:

C#

```
using Zengenti.Contensis.Management;
using Zengenti.Data;
using Zengenti.Search;

var client = ManagementClient.Create();
var websiteProject = client.Projects.Get("website");

var query = new Query(
    Op.Contains("title", "Batman"),
    Op.GreaterThan("runtime", 200)
);

query.OrderBy.Add("-releaseDate")
query.PageIndex = 1;
query.PageSize = 50;

// Execute the search
var results = websiteProject.Entries.Search(query);
```