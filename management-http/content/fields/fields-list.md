1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Content
5.  [Fields](https://www.contensis.com/help-and-docs/apis/management-http/content/fields)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

## Specifying entry fields to return

When getting a single entry or a list of entries, the fields returned in the results can be specified using a comma-separated list of field ids:

JSON

```
GET: /api/management/projects/movieDb/entries/99aae243-ad6e-401b-89f9-90a51def6a18/?fields=title,synopsis,actors
```

If no fields are specified then all the data fields and system fields for an entry will be returned.

## Data fields

Fields defined in the content type for the entry can be specified by their API id.

## System fields

If *sys* is included in the list of fields, then all system fields will be returned for the entry.

If *sys* is not included in the list of fields, then the following system fields will be returned:

-   id
-   dataFormat
-   contentTypeId
-   language
-   versionStatus

Additional system fields can be specified to be returned by being prefixed with *sys.*, e.g.

JSON

```
GET: /api/management/projects/movieDb/entries/99aae243-ad6e-401b-89f9-90a51def6a18/?fields=sys.id,sys.language,sys.contentTypeId
```

The optional system fields that can be specified are:

-   projectId
-   contentTypeId
-   metadata
-   properties
-   version
-   owner

It is not possible to specify individual fields within the *properties* and *metadata* fields.

### Entry title field

The *entryTitle* field is included then this field will be returned, for example:

JSON

```
GET: /api/management/projects/movieDb/entries/99aae243-ad6e-401b-89f9-90a51def6a18/?fields=sys.id,sys.language,sys.contentTypeId,entryTitle
```

### Entry description field

The *entryDescription* field is included then this field will be returned, for example:

JSON

```
GET: /api/management/projects/movieDb/entries/99aae243-ad6e-401b-89f9-90a51def6a18/?fields=sys.id,sys.language,sys.contentTypeId,entryTitle,entryDescription
```