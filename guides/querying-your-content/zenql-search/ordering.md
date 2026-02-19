## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

Dark mode

-   -   [Back to user guides](https://www.contensis.com/help-and-docs/guides)
        
        #### Querying your content
        
    
    -   -   [Overview](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/overview)
        -   [Data types](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/data-types)
        -   [Date formats](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/date-formats)
        -   [Keywords](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/keywords)
        -   [Operators](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/operators)
        -   [Functions](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/functions)
        -   [Relative time period](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/relative-time-period)
        -   [Ordering](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/ordering)
        -   [Cheat sheet](https://www.contensis.com/help-and-docs/guides/querying-your-content/zenql-search/cheat-sheet)
-   End of list

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Querying your content](https://www.contensis.com/help-and-docs/guides/querying-your-content)
4.  ZENQL search

## Order list: ORDER BY {}

Order a list of results by a field of the data returned – supports text, numbers and dates.

-   Order plants by their title.  
    `sys.contentTypeId = plants ORDER BY entryTitle`
-   Order plants by their title in alphabetical order, then by their price in descending order highest price to lowest.  
    `sys.contentTypeId = plants ORDER BY entryTitle asc, price desc`

## Ascending order: ASC

Order the list of results in ascending order.

-   Order plants by their title (A-Z).  
    `sys.contentTypeId = plants ORDER BY entryTitle asc`
-   Order plants by their price, lowest to highest.  
    `sys.contentTypeId = plants ORDER BY price asc`

## Descending order: DESC

Order the list of results in descending order.

-   Order plants by their title (Z-A).  
    `sys.contentTypeId = plants ORDER BY entryTitle desc`
-   Order pots by their height, tallest to shortest.  
    `sys.contentTypeId = pots ORDER BY height desc`