## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Tags

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 02 July 2025

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Examples](#examples)

Get a list of all tags, tags belonging to a particular group, or supply options to find tags with a simple query or provide additional refinements.

## Call signatures

TypeScript

```
list(): Promise<PagedList<Tag>>;

list(groupId: string): Promise<PagedList<Tag>>;

list({
    groupId?: string;
	language?: string;
	order?: string[];
	pageOptions?: PageOptions;
	q?: string;
}: TagListOptions): Promise<PagedList<Tag>>;
```

## Parameters

Name

Type

Description

groupId

`string`

The tag GUID identifier

options

`TagListOptions`

An options object to find tags with a simple query, in a specific groupId or language, provide paging options or to order results by specific tag fields

## Returns

A Promise that will resolve with a [PagedList](https://www.contensis.com/help-and-docs/apis/management-js/model/paged-list) of [Tag](https://www.contensis.com/help-and-docs/apis/management-js/model/tag)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Examples

Get a list of all tags in any group (with the pageSize set in the client config)

TypeScript

```
const tags = await client.tags.list();

console.log(`Found ${tags.totalCount} tags`);

if (tags.totalCount > tags.pageSize)
    console.log(`Showing the first ${tags.pageSize}/${tags.totalCount}`);

for (const tag of tags.items) {
    console.log(`${tag.groupId}: ${tag.value} ${tag.label['en-GB']}`);
}
```

Get a list of tags in a specific group (with the pageSize set in the client config)

TypeScript

```
const tags = await client.tags.list("topics");

console.log(`Found ${tags.totalCount} tags in Topics`);
```

Get a list of tags from a specific tag group, filtered by a query in a specific language, results to be ordered by label, then by modified date descending, requesting the second page while returning (up to) 100 tags in each page

TypeScript

```
const tags = await client.tags.list({
    groupId: "topics",
    q: "Books",
    language: "en-GB",
    pageOptions: {
        pageSize: 100,
        pageIndex: 1
    },
    order: ["label", "-version.modifed"]
});

console.log(`Page ${tags.pageIndex + 1} of ${tags.pageCount}`);

for (const tag of tags.items) {
    console.log(`${tag.value} ${tag.label['en-GB']}`);
}
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Examples](#examples)