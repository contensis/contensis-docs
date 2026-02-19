1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

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