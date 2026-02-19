1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)

[Log in to add to favourites](/account/login)

Page last updated 29 May 2024

ZenQL stands for Zengenti Query Language. It provides a flexible way to search for content and other resources in Contensis. ZenQL can be passed as a HTTP GET request using a query parameter named `zenql`. It gives you an efficient and fluent alternative to the exisiting JSON-based search available in our [APIs](/help-and-docs/apis/all-apis).

The grammar used by ZenQL is separated from specific data schemas. The operators, functions, and relative time periods of ZenQL can be used across all our APIs, apart from a few exceptions where they are not semantically applicable.

## ZenQL Syntax

A query in ZenQL (also known as a “clause”) consists of a field, followed by an operator, followed by one or more values or functions and optional keywords.

-   **Field** – the first component of a ZenQL clause that refers to the attribute or type of information you are querying e.g. a field in an entry, or an attribute of a user.
-   **Operator** - the part of the clause that relates or compares a function or value with the field that precedes it.
-   **Value** – the part of the clause that describes the content you are querying based on the information stored in its field.
-   **Keyword** - a word or phrase that serves a specific purpose in defining your query, such as linking two clauses or altering the logic of a clause or operator.

### Syntax examples

Searching for all entries that are of the plant content type.

`sys.contentTypeId = plant`

Plant entries that have been created this week.

`sys.contentTypeId = plant and sys.version.created >= startOfWeek()`

### Find the full list of keywords, operators, functions and field references along with additional resources here: