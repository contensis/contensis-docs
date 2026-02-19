-   [And](#and)
-   [Or](#or)
-   [Not](#not)
-   [Between](#between)
-   [Contains](#contains)
-   [EndsWith](#endswith)
-   [EqualTo](#equalto)
-   [Exists](#exists)
-   [FreeText](#freetext)
-   [GreaterThan](#greaterthan)
-   [GreaterThanOrEqualTo](#greaterthanorequalto)
-   [In](#in)
-   [LessThan](#lessthan)
-   [LessThanOrEqualTo](#lessthanorequalto)
-   [StartsWith](#startswith)
-   [DistanceWithin](#distancewithin)

## Logical operators

### And

This would return any document where *first* is *1* AND *second* is *2*

TypeScript

```
const query = new Query(
  Op.and(
    Op.equalTo('first', 1),
    Op.equalTo('second', 2)
  )
);
```

The *And* operator is the default logical operator and is not required for top-level query expressions

TypeScript

```
const query = new Query(
  Op.equalTo('first', 1),
  Op.equalTo('second', 2)
);
```

### Or

The example would return any document where *first* is *1* OR *second* is *2*

TypeScript

```
const query = new Query(
  Op.or(
    Op.equalTo('first', 1),
    Op.equalTo('second', 2)
  )
);
```

### Not

The *not* expects an inner operator so in the example any document where *first* is NOT equal to *7* would be returned

TypeScript

```
const query = new Query(
  Op.not(
    Op.equalTo('first', 1)
  )
);
```

## Relational & equality operators

### Between

In this example, if our field is between *18* and *45* inclusive it would match

TypeScript

```
const query = new Query(
  Op.between('age', 18, 45)
);
```

### Contains

This would match on a field called *description* containing the phrase *batman*. This operator can also use ? and \* wildcards. However, it can be slow to search longer fields and for performance reasons it does not include entries that have more than 8,000 characters in that field. Unless essential, it is recommended that this operator is avoided as it is highly resource intensive. Where possible, such as searching efficiently for complete words across the whole field, you should use the FreeText operator.

TypeScript

```
const query = new Query(
  Op.contains('description', 'batman')
);
```

### EndsWith

This would find any item that has a field called *wordField* with a value ending with *ing*. Note that for performance reasons this operator does not search entries that have a text field with more than 8,000 characters in that field.

TypeScript

```
const query = new Query(
  Op.endsWith('wordField', 'ing')
);
```

### EqualTo

This would find any item that has a field called *blends* with a value exactly matching *5*. For string fields, the comparison is case-insensitive. Note that for performance reasons this operator does not search entries that have a text field with more than 8,000 characters in that field.

TypeScript

```
const query = new Query(
  Op.equalTo('blends', 5)
);
```

### Exists

In the example any document that has a field called *fieldName* and would be returned. Documents where *fieldName* has some content would also be returned.

You can use a value of *false* if you want documents that do not contain a given field or where the field is empty or null

TypeScript

```
const query = new Query(
  Op.exists('fieldName', false)
);
```

### FreeText

In the next example the field *synopsis* is searched upon for all words that match *gotham* and *dark* and *knight*

TypeScript

```
const query = new Query(
  Op.freeText('synopsis', 'gotham dark night')
);
```

#### *Fuzzy* freeText search

The example is performing a *fuzzy* search, which returns entries that contain terms similar to the search terms, as measured by a [Levenshtein edit distance](https://en.wikipedia.org/wiki/Levenshtein_distance). An edit distance is the number of one-character changes needed to turn one term into another. These changes can include:

-   Changing a character (**b**ox → fox)
-   Removing a character (**b**lack → lack)
-   Inserting a character (sic → sic**k**)
-   Transposing two adjacent characters (act → cat)

To find similar terms, the fuzzy query creates a set of all possible variations, or expansions, of the search term within a specified edit distance. The query then returns exact matches for each expansion.

We use the preferred auto [setting](https://www.elastic.co/guide/en/elasticsearch/reference/current/common-options.html#fuzziness) for fuzziness, this means that the edit distance changes dependant on the length of the search terms.

TypeScript

```
const query = new Query(
  Op.freeText('synopsis', 'gotham dark night', true)
);
```

#### Operator 'or'

The following example changes the default search operator from *and* to *or* so that the field *synopsis* is searched upon for any words that match *gotham* or *dark* or *knight*

TypeScript

```
const query = new Query(
  Op.freeText('synopsis', 'gotham dark night', false, 'or')
);
```

### GreaterThan

In the example any item that has a field called *first* and a value that is greater than *7* would be returned

TypeScript

```
const query = new Query(
  Op.greaterThan('first', 7)
);
```

### GreaterThanOrEqualTo

In the example any item that has a field called *first* and a value that is greater than or equal to *7* would be returned

TypeScript

```
const query = new Query(
  Op.greaterThanOrEqualTo('first', 7)
);
```

### In

In the example any document that where the field *first* is equal to *1*,*7* or *11* would be returned. The values should be of the same type, in this case *integer*.

TypeScript

```
const query = new Query(
  Op.in('first', 1, 7, 11)
);
```

### LessThan

In the example any item that has a field called *first* and a value that is less than *7* would be returned

TypeScript

```
const query = new Query(
  Op.lessThan('first', 7)
);
```

### LessThanOrEqualTo

In the example any item that has a field called *first* and a value that is less than or equal to *7* would be returned

TypeScript

```
const query = new Query(
  Op.lessThanOrEqualTo('first', 7)
);
```

### StartsWith

In the example if the *name* field contains a value starting with *war* it would match. Note that for performance reasons this operator does not search entries that have a text field with more than 8,000 characters in that field.

TypeScript

```
const query = new Query(
  Op.startsWith('name', 'war')
);
```

### DistanceWithin

In the example any locations within a 10 mile radius of the specified location would match

TypeScript

```
const query = new Query(
  Op.distanceWithin("location", 52.377, -2.749, "10mi")
);
```