1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 29 May 2025

## On this page

-   [Properties](#parameters)
-   [QueryAggregation](#query-aggregation)

Provides insights into data distribution and prompts for further search refinements. [Aggregations](/help-and-docs/apis/delivery-http/search-basics/aggregations) allow you to group data by specific fields and return a count of entries matching each unique value from all pages in a result-set.

`QueryAggregations` is a structure that is used to add aggregations to a search query and to describe the options for aggregating the data assigned to an entry field.

## Properties

Name

Type

Description

<aggregation>

[`QueryAggregation`](#query-aggregation)

Provide a key to add your aggregation query options and to group your aggregates by in the search response

## QueryAggregation

Name

Type

Description

field

`string`

The API ID of the entry field containing the data to aggregate

missing

`string`

Include an additional aggregate with this name for entry fields that do not have a value assigned

size

`number`

The number of top aggregates to return in the results

### Additional considerations

Aggregations that reference array fields *do not* require square brackets \[\] to be specified in the field

Due to technical limitations, we can not create aggregations using any of the following reserved words: `_as_string`, `after_key`, `bg_count`, `bottom_right`, `bounds`, `buckets`, `count`, `doc_count`, `doc_count_error_upper_bound`, `fields`, `from`, `from_as_string`, `geometry`, `hits`, `key`, `key_as_string`, `keys`, `location`, `max_score`, `meta`, `min`, `min_length`, `properties`, `score`, `sum_other_doc_count`, `to`, `to_as_string`, `top`, `top_left`, `total`, `type`, `value`, `value_as_string`, `values`

## On this page

-   [Properties](#parameters)
-   [QueryAggregation](#query-aggregation)