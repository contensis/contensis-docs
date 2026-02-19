An operator in ZenQL is one or more symbols or words which compares the value of a field on its left with one or more values or functions to its right. Only true results are retrieved by the query.

## Predicate operators

### Equal to: =

All entries of the content type *plant*.

`sys.contentTypeId = plant`

All entries where the description field *is empty.*

`description = NULL`

### Not equal to: !=

The exclamation mark before the equals sign can be used to negate the result of an equal to operator. This example will show all entries that are not from the *plant* content type.

`sys.contentTypeId != plant`

All entries where the description field *is not* empty (i.e. the field exists and is not null, which for text data would include having an empty string).

`description != NULL`

### Contains: ~

Search for all entries with a field called description containing the phrase *fern*. This operator only searches the first 8,000 characters of the field. To search efficiently for complete words across the whole field, use the FREETEXT operator.

`description ~ fern`

### Does not contain: !~

Search for all entries with a field called description that does not contain the phrase *fern*. This operator only searches the first 8,000 characters of the field. To search efficiently for complete words across the whole field use the FREETEXT operator.

`description !~ fern`

### Greater than: >

All entries where the field height is greater than 100.

`height > 100`

### Less than: <

All entries where the field height is less than 100.

`height < 100`

### Greater than or equal to: >=

All entries with a height of 100 or greater.

`height >= 100`

### Less than or equal to: <=

All entries with a height of 100 or less.

`height <= 100`

### IN

All entries that have a plantType value from the list, either palm or cacti or ferns. *e.g. Show me all plants that are palms, cacti or ferns.*

`plantType IN (palm, cacti, ferns)`

### NOT IN

All entries that do not have a *plantType* value from the list, either *palm* or *cacti* or *ferns.* For example, *Show me all plants that are not palms, cacti or ferns.*

`plantType NOT IN (palm, cacti, ferns)`

### EXISTS

All entries that have a *latinName* field.

`latinName EXISTS`

### NOT EXISTS

All entries that do not have a *latinName* field.

`latinName NOT EXISTS`

### STARTSWITH

All entries with a title value that begins with the case-insensitive string *Chine.*

`title STARTSWITH Chine`

### NOT STARTSWITH

All entries with a title value that does not start with the case-insensitive string *Chine.*

`title NOT STARTSWITH Chine`

### ENDSWITH

All entries with a title value that ends with the case-insensitive string *s.*

`title ENDSWITH s`

### NOT ENDSWITH

All entries with a title value that does not end with the case-insensitive string *s.*

`title NOT ENDSWITH s`

### DistanceWithin

DistanceWithin provides a proximity search based on a latitude and longitude. All entries with a *plantOrigin* lat-lon value within a 100km radius of the stated coordinates.

`plantOrigin DistanceWithin(25.1363888,97.3733773, 100km)`

### NOT DistanceWithin

DistanceWithin provides a proximity search based on a latitude and longitude. All entries with a *plantOrigin* lat-lon value outside of a 100km radius of the stated coordinates.

`plantOrigin NOT DistanceWithin(25.1363888,97.3733773, 100km)`

### FREETEXT

All entries with a description field containing both words *your* and *home*.

`description FREETEXT “your home”`

**\* FREETEXT: Any field containing the string**

All entries with any field containing the string *interior.*

`* FREETEXT interior`

**\* FREETEXT: Any field containing multiple specified words**

All entries with any field containing both words *your* and *home*.

`* FREETEXT “your home”`

**FREETEXT with title field boosted**

All entries with the word Boston, but bring entries with Boston in their title higher in the search results by boosting the title field.

`title^80 FREETEXT “Boston”`

### NOT FREETEXT

All entries where the description field does not contain the words *your home.*

`description NOT FREETEXT “your home”`

## Operator API support

**Operator**

**Entries**

**Users & Groups**

Equal to

✅

✅

Not Equal to

✅

✅

Contains

✅

✅

Does not contain

✅

✅

Greater than

✅

✅

Less Than

✅

✅

Greater than or equal to

✅

✅

Less than or equal to

✅

✅

In

✅

✅

Not in

✅

✅

Exists

✅

\-

Not exists

✅

\-

Starts with

✅

✅

Not starts with

✅

✅

Distance proximity

✅

\-

Outside distance proximity

✅

\-

Freetext

✅

✅

Not freetext

✅

✅