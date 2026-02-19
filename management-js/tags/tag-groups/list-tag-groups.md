## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Tags
5.  Tag groups

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 02 July 2025

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Examples](#examples)

Get a list of all tag groups, or provide options to find tag groups with a simple query

## Call signatures

TypeScript

```
list(): Promise<PagedList<TagGroup>>;

list({
	language?: string;
	order?: string[];
	pageOptions?: PageOptions;
	q?: string;
}: TagGroupListOptions): Promise<PagedList<TagGroup>>;
```

## Parameters

Name

Type

Description

options

`TagGroupListOptions`

An options object to find tag groups with a simple query, provide paging options or order results by specific fields

## Returns

A Promise that will resolve with a [PagedList](https://www.contensis.com/help-and-docs/apis/management-js/model/paged-list) of [TagGroup](https://www.contensis.com/help-and-docs/apis/management-js/model/tag-group)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Examples

Get a list of all tag groups (with the pageSize set in the client config)

TypeScript

```
const tagGroups = await client.tags.groups.list();

console.log(`Found ${tagGroups.totalCount} tag groups`);

for (const tagGroup of tagGroups.items) {
    console.log(`${tagGroup.name} has ${tagGroup.tagCount} tags`);
}
```

Get a list of tag groups, filtered by a query in a specific language, results to be ordered by name, then by modified date descending, requesting the second page while returning (up to) 10 tag groups in each page

TypeScript

```
const tagGroups = await client.tags.groups.list({
    q: "topics",
    language: "en-GB",
    pageOptions: {
        pageSize: 10,
        pageIndex: 1
    },
    order: ["name", "-version.modifed"]
});

console.log(`Page ${tagGroups.pageIndex + 1} of ${tagGroups.pageCount}`);

for (const tagGroup of tagGroups.items) {
    console.log(`${tagGroup.name} has ${tagGroup.tagCount} tags`);
}
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Examples](#examples)