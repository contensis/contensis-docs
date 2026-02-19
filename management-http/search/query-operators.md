-   And
-   Or
-   Not
-   Between
-   Contains
-   endsWith
-   equalTo
-   Exists
-   freeText
-   greaterThan
-   greaterThanOrEqualTo
-   In
-   lessThan
-   lessThanOrEqualTo
-   startsWith
-   distanceWithin

## Logical operators

### And

This would return any document where *first* is *1* AND *second* is *2*.

JSON

```
{
    "where": [{
        "and": [{
            "field": "first",
            "equalTo": 1
        }, {
            "field": "second",
            "equalTo": 2
        }]
    }]
}
```

The *And* operator is the default logical operator and is not required to be specified explicitly.

JSON

```
{
    "where": [{
        "field": "first",
        "equalTo": 1
    }, {
        "field": "second",
        "equalTo": 2
    }]
}
```

### Or

The example would return any document where *first* is *1* OR *second* is *2*.

JSON

```
{
    "where": [{
        "or": [{
            "field": "first",
            "equalTo": 1
        }, {
            "field": "second",
            "equalTo": 2
        }]
    }]
}
```

### Not

The *not* expects an inner operator so in the example any document where *first* is NOT equal to *7* would be returned.

JSON

```
{
    "where": [{
        "not": {
            "field": "first",
            "equalTo": 7
        }
    }]
}
```

## Relational & equality operators

### Between

In this example, if our field is between *18* and *45* inclusive it would match.

JSON

```
{
    "where": [{
        "field": "age",
        "between": [18, 45]
    }]
}
```

### Contains

This would match on a field called *description* containing the phrase *batman*. This operator can also use ? and \* wildcards. However, it can be slow to search longer fields and for performance reasons it does not include entries that have more than 8,000 characters in that field. Unless essential, it is recommended that this operator is avoided as it is highly resource intensive. Where possible, such as searching efficiently for complete words across the whole field, you should use the FreeText operator.

If you carried out a search with the term *bat* or *man* or *batma*, each of the searches would return results for *batman* as the terms are contained within the word.

JSON

```
{
    "where": [{
        "field": "description",
        "contains": "batman"
    }]
}
```

#### Multi word

If your description field contained the phrase batman begins, and you carried out a search containing multiple words, results would be returned for *batman, batman beg*, but not for *batman ends.*

JSON

```
{
    "where": [{
        "field": "description",
        "contains": "batman begins"
    }]
}
```

### endsWith

This would find any item that has a field called *wordField* with a value ending with *ing*. Note that for performance reasons this operator does not search entries that have a text field with more than 8,000 characters in that field.

JSON

```
{
    "where": [{
        "field": "wordField",
        "endsWith": "ing"
    }]
}
```

### equalTo

This would find any item that has a field called *blends* with a value exactly matching *5*. For string fields, the comparison is case-insensitive. Note that for performance reasons this operator does not search entries that have a text field with more than 8,000 characters in that field.

JSON

```
{
    "where": [{
        "field": "blends",
        "equalTo": 5
    }]
}
```

### Exists

In the example any document that has a field called *fieldName* and would be returned. Documents where *fieldName* has some content would also be returned.

You can use a value of *false* if you want documents that do not contain a given field or where the field is empty or null.

JSON

```
{
    "where": [{
        "field": "fieldName",
        "exists": true
    }]
}
```

### freeText

In the example the field *synopsis* is searched upon for all words that match *gotham* and *dark* and *knight*.

JSON

```
{
    "where": [{
        "field": "synopsis",
        "freeText": "gotham dark knight"
    }]
}
```

#### Operator 'or'

By default freeText matches *all* words in the search term. If you want results that match one or more words in the search term the operator can be set to "or". Results that match the most number of words in the search term are ranked higher than documents that match fewer words.

JSON

```
{
   "where":[
      {
         "field":"synopsis",
         "freeText":{
            "term":"gotham dark knight",
            "operator":"or"
         }
      }
   ]
}
```

#### Fuzzy

Free text searches can also be made fuzzy, by specifying fuzzy true and passing the search value as term.

JSON

```
{
   "where":[
      {
         "field":"synopsis",
         "freeText":{
            "term": "gotham dark knight",
            "fuzzy": true
         }
      }
   ]
}
```

A fuzzy search returns results that contain terms similar to the search term. The similarity is measured by a [Levenshtein](https://en.wikipedia.org/wiki/Levenshtein_distance) edit distance.

An edit distance is the number of one-character changes needed to turn one term into another. These changes can include:

-   Changing a character (**b**ox → fox)
-   Removing a character (**b**lack → lack)
-   Inserting a character (sic → sic**k**)
-   Transposing two adjacent characters (act → cat)

To find similar terms, the fuzzy query creates a set of all possible variations, or expansions, of the search term within a specified edit distance. The query then returns exact matches for each expansion.

We use the preferred `auto` [setting](https://www.elastic.co/guide/en/elasticsearch/reference/current/common-options.html#fuzziness) for fuzziness, this means that the edit distance changes dependant on the length of the search terms.

### greaterThan

In the example any item that has a field called *first* and a value that is greater than *7* would be returned.

JSON

```
{
    "where": [{
        "field": "first",
        "greaterThan": 7
    }]
}
```

### greaterThanOrEqualTo

In the example any item that has a field called *first* and a value that is greater than or equal to *7* would be returned.

JSON

```
{
    "where": [{
        "field": "first",
        "greaterThanOrEqualTo": 7
    }]
}
```

### In

In the example any document where the field *first* is equal to *1*,*7* or *11* would be returned. The values should be of the same type, in this case *integer*.

JSON

```
{
    "where": [{
        "field": "first",
        "in": [1, 7, 11]
    }]
}
```

### lessThan

In the example any item that has a field called *first* and a value that is less than *7* would be returned.

JSON

```
{
    "where": [{
        "field": "first",
        "lessThan": 7
    }]
}
```

### lessThanOrEqualTo

In the example any item that has a field called *first* and a value that is less than or equal to *7* would be returned.

JSON

```
{
    "where": [{
        "field": "first",
        "lessThanOrEqualTo": 7
    }]
}
```

### startsWith

In the example if the *name* field contains a value starting with *war* it would match. Note that for performance reasons this operator does not search entries that have a text field with more than 8,000 characters in that field.

JSON

```
{
    "where": [{
        "field": "name",
        "startsWith": "war"
    }]
}
```

### distanceWithin

In the example any locations within a 10 mile radius of the specified location would match.

JSON

```
{
    "where": [{
        "field": "location",
        "distanceWithin": {
            "lat": "52.377",
            "lon": "-2.749",
            "distance": "10mi"
        }
    }]
}
```