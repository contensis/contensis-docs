1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-http)
4.  [Search basics](https://www.contensis.com/help-and-docs/apis/delivery-http/search-basics)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 16 July 2020

Search queries can be focused by weighting free-text queries and structuring queries so as to provide convergence on certain fields and/or terms.

FreeText queries can be weighted in order to provide focus on certain terms. This is achieved by modifying the relevance of each search result by the provided weighting - the higher the relevance of any given result, the higher it will appear in the list.

Weighting can be used to provide more relevance to certain fields for your results - for example, if searching across movies, you may feel any results in the ‘title’ field are more relevant than the ‘tagline’ or ‘overview’ fields. This is easily achieved by simply weighting the relevant free-text operator in the query, as will be shown below.

A more subtle use of weighting can be applied to give more relevance to certain terms within a specific field.

Weighting can be achieved through the use of the **.Weight()** operator, or through the use of query structure. Examples of both are outlined below.

## FreeText

### Providing more relevance for specific fields

Weighting can be used to provide more relevance to specific fields with a query.

For example, if searching across movie ‘title’, ‘tagline’ and ‘overview’ for the term ‘earth’, with an emphasis on the ‘title’ field, you could use the following query:

As can be seen from the following results, this lends a higher relevance to titles with a higher ratio of the term ‘earth’:

![Field search example - weighted by title](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/01-field-search-title-weighted.xf31bd751.png?q=80&f=webp)

However, what can also be seen is the fact that ‘title’ fields with higher ratios of the term do not guarantee higher relevance. This is due to the cumulative effect of scoring across terms and operators, meaning the total relevance of the result can also be affected by the relevance of the other fields which have been searched across.

Applying the same weighting to the ‘tagline’ field:

Yields the following results:

![Field search example - weighted by tagline](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/02-field-search-tagline-weighted.x8c6b5b47.png?q=80&f=webp)

Finally, weighting the ‘overview’ field:

Results in:

![Field search example - weighted by overview](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/03-field-search-overview-weighted.xb0e0f29b.png?q=80&f=webp)

As can be seen, weighting can help in providing relevance to your results, but is not a guarantee of specific ordering.

### Providing more relevance to terms within a field

Weighting can be used to provide focus on terms in free-text searches.

For example, if searching across movie overviews for ‘thrillers’ which are ‘exciting’ and/or ‘tense’, you might use the following query:

However, as can be seen from the results, this also retrieves movies which are not thrillers, but are apparently exciting and/or tense:

![Term search example - not weighted](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/04-term-search-not-weighted.x6c45c024.png?q=80&f=webp)

We can favour ‘thrillers’ by adding weighting to the query as follows:

The query will now favour ‘thrillers’ over other movie results as can be seen in the following:

![Term search example - weighted by thriller](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/05-term-search-thriller-weighted.xfbd9aa5d.png?q=80&f=webp)

However, ‘exciting’ and ‘tense’ are still not favoured over other results. By also weighting these queries, we can push them to the top:

As can be seen from the results:

![Term search example - weighted by all](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/06-term-search-all-weighted.xb3d82a14.png?q=80&f=webp)

Please note the different weights for ‘thriller’, ‘exciting’ and ‘tense’: this difference is required in order to prevent the weightings negating each other. For example:

As can be seen from the results, weighting each of these terms identically negates the effect, producing the same result as the non-weighted query:

![Term search example - weighted equally](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/07-term-search-all-equally-weighted.x9f092da0.png?q=80&f=webp)

## Query Structure

As well as weighting, query structure can be used to provide focus in searches. Continuing with the example in weighting free-text searches, we will show how query structure can be used to obtain the same results.

### Providing more relevance for specific fields

Query structure can also be used to provide more relevance to specific fields. For example, structuring a query as follows gives a relevance boost to any documents matching the query for the ‘title’ field:

This yields the following results:

![Field search example - structured weighted](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/08-field-search-title-structured-weighted.xfff64af5.png?q=80&f=webp)

However, this does not produce the same results as those of the weighted example.

### Providing more relevance to terms within a field

As in the weighted examples, the focus of the query should be ‘thrillers’, with ‘tense’ and ‘exciting’ being adjectives which should be favoured. This can be achieved by restructuring the original query as follows:

As you can see from the results, this pushes the exciting and tense thrillers to the top of the results, while also removing any movies which are not also thrillers:

![Term search example - structured weighting](https://www.contensis.com/image-library/resources-images/developer-documentation-images/query-weighting/09-term-search-structured-weighted.xb462b22f.png?q=80&f=webp)

**NOTE: Other Terms**  
Query weighting will have no effect on the ordering of the results of the following queries:

-   EqualTo
-   Between
-   Contains
-   EndsWith
-   StartsWith
-   GreaterThan
-   GreaterThanOrEqualTo
-   In
-   LessThan
-   LessThanOrEqualTo

Entries either can, or cannot, satisfy these query specifications. Therefore, weighting will not affect the ordering of these results as the relevance of each will be identical.