Search for entries using a query tree structure, along with order and paging specifiers, allows a search to be performed against indexed documents held in ElasticSearch. The query API allows any required sub-query structure to be defined and a comprehensive selection of [Operators](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/search/query-operators) enable individual field level evaluation.

-   [Query](#query)
-   [Sub-queries](#sub-queries)
-   [Paging](#paging)
-   [Ordering](#ordering)
-   [Weighting](#weighting)
-   [Specifying fields](#specifying-fields)
-   [Limiting fields](#limiting-fields)
-   [Resolving field content](#resolving-field-content)
-   [Aggregate field content](#aggregate-field-content)
-   [Location searches](#location-searches)
-   [Ordering by distance](#ordering-by-distance)
-   [Complete example](#complete-example)

TypeScript

```
search(query: Query): Promise<PagedSearchList<Entry>>

search(query: Query, linkDepth: number): Promise<PagedSearchList<Entry>>
```

## Query

This example demonstrates a simple search with default ordering and paging options.

Search for all entries where the title field contains "Batman" and the runtime is greater than 200

TypeScript

```
import { Query, Op } from "contensis-delivery-api";

const query = new Query(
  Op.contains('title', 'Batman'),
  Op.greaterThan("runtime", 200)
);

const films = await client.entries.search(query);

// films.pageIndex
// films.pageSize
// films.totalCount
// films are available
if (films.items.length > 0) {
  for (const film of films.items) {
    console.log(film.entryTitle);
    console.log(film.tagline);
  }
}
```

## Sub-queries

A sub-query is a query within another query that is used as a condition to further restrict the results. Effectively they are defined by an explicit nesting of [logical operators](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/search/query-operators).

This example demonstrates a simple search with a sub-query.

Search for all entries where the title field contains "Batman" and either the release date is greater than 1960 or the tagline contains "gotham"

TypeScript

```
const query = new Query(
  Op.contains('title', 'Batman'),
  Op.or(
    Op.greaterThan('releaseDate', 1960),
    Op.contains('tagline', 'gotham')
  )
);
```

Because of the way that search data is stored and query responses are cached, it is most efficient for queries on sys.contentTypeId, sys.versionStatus, sys.dataFormat and sys.language to be at the top level of the query, rather than in subqueries. For example, the following is very efficient:

TypeScript

```
const query = new Query(
    Op.equalTo('sys.contentTypeId', 'content'), 
    Op.equalTo('sys.language', 'en-GB'),
    Op.equalTo('sys.versionStatus', 'published')
);
```

However, this second example, which results in the same query, will take longer to process and not be cached as effectively:

TypeScript

```
const query = new Query(
    Op.or(
        Op.equalTo('sys.contentTypeId', 'content')
    ),
    Op.and(
        Op.equalTo('sys.language', 'en-GB'),
        Op.equalTo('sys.versionStatus', 'published')
    )
);
```

## Paging

Paging allows the number of results to be restricted to a defined count so that the results are easier to handle and ensures a response is returned quickly. The page number can also be specified to define which set of results is to be returned.

If you intend to page through the complete result set without any duplicates you should always specify an order by field. The page size is limited to a maximum of 10,000, however this is not recommended.

Fetch 50 results per page and request the second page of results

TypeScript

```
query.pageSize = 50;
query.pageIndex = 1;
```

## Ordering

Results can be ordered by one or more fields in an ascending or descending direction. Order clauses are prioritised in the order that they are added. By default, if no order clauses are specified then the entry results are ordered by:

-   A relevancy 'score' for each entry for the search query (from ElasticSearch) in a descending direction
-   The EntryTitle in an ascending direction.

This is the best solution for searches using a search term of some kind as it will promote the most relevant results to the top of the results. However, this can occasionally mean that an odd entry might appear on more than one page as the relevancy score is dynamically calculated on each paged request. As such, if you intend to page through the complete result set without any duplicates you should always specify an order by field.

TypeScript

```
import { OrderBy } from "contensis-delivery-api";
```

JavaScript

```
const { OrderBy } = require("contensis-delivery-api");
```

### Ascending order

Order by 'releaseDate' in an ascending direction

TypeScript

```
query.orderBy = OrderBy.asc('releaseDate');
```

### Descending order

Order by 'releaseDate' in a descending direction

TypeScript

```
query.orderBy = OrderBy.desc('releaseDate');
```

### Multiple clauses

Multiple order clauses.

Multiple order clauses applied in the supplied precedent - one after another

TypeScript

```
query.orderBy = OrderBy.asc('title').desc('releaseDate');
```

## Weighting

All query operators can have a weight applied.

Find all entries where the first field is 7 and boost the weight of any results matched with this criteria by 10

TypeScript

```
const query = new Query(
  Op.equalTo('first', 7).weight(10)
);
```

## Specifying fields

### System fields

System fields such as id, contentTypeId, projectId, versionNo etc. are under the [sys](https://www.contensis.com/help-and-docs/apis/delivery-js/model/entry) object and can be accessed using a dot notation, e.g. sys.id, sys.contentTypeId, sys.projectId, sys.version.versionNo.

The *entryTitle* field is a dynamic value, determined by the *EntryTitleField* value in the [content type](https://www.contensis.com/help-and-docs/apis/delivery-js/model/content-type), the same applies to *entryDescription* and *entryThumbnail* fields, and will contain the value from the content type field that has been set to represent these common entry fields.

### Data fields

Fields defined in the content type for the entry can be accessed by their API id.

### All fields

All fields can be searched by specifying an asterisk (\*) in the field id. Note there are some limitations, and the FreeText operator is not supported for all fields.

Search for all entries where any field is equal to "Interstellar"

TypeScript

```
const query = new Query(
  Op.equalTo('*', "Interstellar")
);
```

### Array fields

Searching on array fields require square brackets \[\] to be specified in the field id before any field ids within the object. Note that this syntax is not required for single object fields. All operators support searching across array fields.

#### Example array field search

Search all entries for a quote source of "Bruce Willis" within a repeating quote field called 'movieQuote'

TypeScript

```
const query = new Query(
  Op.equalTo('movieQuote[].source', "Bruce Willis")
);
```

## Limiting fields

If you have large entries and only require a subset of fields it is worth limiting the fields returned in the results. This will reduce the size of the payload from the API which in turn will improve performance. You can include fields by specifiying the field API ID or you can exclude fields by prefixing the field API ID with a -. Field limiting also applies to linked entries when specifying a `linkDepth`.

Limit the fields returned in our search results to the fields specified

TypeScript

```
query.fields = ['entryTitle', 'description'];
```

## Resolving field content

Entry fields containing links to other content can have the field content automatically resolved in the search results by adding [linkDepth](https://www.contensis.com/help-and-docs/apis/delivery-js/entries/resolve-entry-links) parameter to our search set to the number of levels that all child fields containing linked content will be resolved to

Keeping check on payload sizes when using linkDepth of more than 0, we can also set `fieldLinkDepths` in the query, specifying which entry link field(s) require link depth resolving and to what depth.

Resolve entry fields in search results to a depth specified for each field containing linked content we would like resolved

TypeScript

```
query.fieldLinkDepths = { 'linkField': 2, 'otherField': 1 };
```

## Aggregate field content

Provide insights into data distribution and prompt for further search refinements. [Aggregations](https://www.contensis.com/help-and-docs/apis/delivery-http/search-basics/aggregations) allow you to group data by specific fields and return a count of entries matching each unique value from all pages in the result-set.

Add an `aggregations` object in the shape of [`QueryAggregations`](https://www.contensis.com/help-and-docs/apis/delivery-js/model/query-aggregations) to the query, and define one or more aggregations that contain the field to count, whether we will consider unpopulated fields, and limit the amount of aggregated values to return.

Aggregations that reference array fields *do not* require square brackets \[\] to be specified in the field

The top aggregated values for each aggregation will be returned in the search response, grouped under each defined aggregation, along with the paged list of search results.

### Example

Count each unique value of an entry field called entryTags, grouping the aggregates for this field inside an object called tags, count each entry containing no value under an aggregate called Untagged, and return only the top 5 aggregates.

TypeScript

```
query.aggregations = {
    tags: {
      field: 'entryTags',
      missing: 'Untagged',
      size: 5
    }
  };
```

## Location searches

Search for locations within a radius of a specified location.

### Supported distance units

Unit

Search value

Mile

mi or miles

Yard

yd or yards

Feet

ft or feet

Inch

in or inch

Kilometer

km or kilometers

Meter

m or meters

Centimeter

cm or centimeters

Millimeter

mm or millimeters

Nautical mile

NM, nmi or nauticalmiles

### Example

Find all entries which have a location within 10.5 miles of Ludlow Castle's location. Append the search value at the end of the distance specified, so for example "10.5mi" or "10.5miles".

TypeScript

```
const query = new Query(
  Op.distanceWithin("location", 52.377, -2.749, "10mi"))
);
```

When searching for a location field, you can also [order the results by distance](#ordering-by-distance).

## Ordering by distance

When [searching by location](#location-searches), to return the search results according to the distance of the location field in each entry from the distance specified in the distanceWithin search, add the location field to the [orderBy](#ordering) clause.

Search for all entries that have a location field within 10 miles of Ludlow Castle, ordering the results by the nearest to the furthest away.

TypeScript

```
const query = new Query(
  Op.distanceWithin("location", 52.377, -2.749, "10mi")
);

query.orderBy = OrderBy.asc('location');
```

## Complete example

Search for all entries where the title field contains "Batman" and either the release date is greater than 1960 or the tagline contains "gotham". Ordering the results by title and then by descending release date. Each page will return up to 50 results, request the second page of results and limit the returned fields to just entry title, tagline and release date.

TypeScript

```
import { Query, Op, OrderBy } from "contensis-delivery-api";

const query = new Query(
  Op.contains('title', 'Batman'),
  Op.or(
    Op.greaterThan('releaseDate', 1960),
    Op.contains('tagline', 'gotham')
  )
);

query.orderBy = OrderBy.asc('title').desc('releaseDate');
query.pageSize = 50;
query.pageIndex = 1;
query.fields = ['entryTitle', 'tagline', 'releaseDate'];

const films = await client.entries.search(query);

// films.pageIndex
// films.pageSize
// films.totalCount
// films are available
if (films.items.length > 0) {
  for (const film of films.items) {
    console.log(film.entryTitle);
    console.log(film.tagline);
  }
}
```