A keyword in ZenQL is a word or phrase that does any of the following:

-   joins two or more clauses together to form a complex ZenQL query
-   alters the logic of one or more clauses
-   alters the logic of of an operator

You can use the following keywords in your ZenQL queries.

## AND

Used to combine multiple clauses, allowing you to refine a search.

-   Find all plants that are published.  
    `sys.contentTypeId = plant and sys.isPublished = true`

## OR

Used to check if any of the conditions are met in a clause.

-   Find all entries that are plants or pots.  
    `sys.contentTypeId = plant or sys.contentTypeId = pot`

## NOT

Used to ensure that the search condition is not true.

-   Find all entries that are not plants.  
    `not sys.contentTypeId = plant` alternatively `sys.contentTypeId != plant`
-   Find all entries where the entry title does not start with *chinese*.  
    `entryTitle not startswith chinese`

## BETWEEN

Used to search within a range. Can be used with numbers and dates.

-   Find all pots that have a height between 6 and 12 centimetres.  
    `sys.contentTypeId = pot and height between(6,12)`
-   Show all pots created between last month and this month.  
    `sys.contentTypeId = pot and sys.version.created between(startOfMonth(-1),endOfMonth())`

## SCOPE: ()

Scopes using parenthesis allow you to compare and combine multiple complex clauses.

-   Find all plant or pots that were created on or after the 6th December 2021.  
    `sys.contentTypeId = plant or (sys.contentTypeId = pot and sys.version.created >= 2020-12-06`