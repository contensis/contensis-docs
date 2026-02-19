1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 27 August 2024

The SecuritySearchOptions type defines page index, page size, order by and a where query for searching users.

## Properties

Name

Type

Description

OrderBy

`List<string>`

The fields to order the results by.

Where

`IExpression[]`

The where clause to search by

PageIndex

int

The page index to show results for

PageSize

int

The number of results to include in each page