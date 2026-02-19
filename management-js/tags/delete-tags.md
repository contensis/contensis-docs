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

Delete an existing tag by its id, delete a number of tags in a specific tag group, or replace one or more tags with another tag.

## Call signatures

TypeScript

```
delete(id: string, replacementTagId?: string): Promise<void>;

delete({
    groupId: string;
    ids: string[];
}: TagBulkDeleteOptions, replacementTagId?: string): Promise<IBulkDeletedTags>;
```

## Parameters

Name

Type

Description

id

`string`

The GUID identifier of the tag to delete

options

`TagBulkDeleteOptons`

An options object containing an array of tag `ids` to delete and the `groupId` the tags belong to

replacementTagId

`string`

Optional GUID identifier of the tag to replace references to deleted tag(s) with wherever they are used

## Returns

A Promise that will resolve with no data, or where we are bulk deleting tags a Promise that will resolve with an `IBulkDeletedTags` response.

## Remarks

A tag cannot be deleted if it is used in any assets or entries however it can be deleted and have its references replaced (or merged) with another tag that exists in the same tag group

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Examples

Delete an unused tag by its id

TypeScript

```
await client.tags.delete("109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c");
```

Delete multiple unused tags from a specific tag group by their ids

TypeScript

```
await client.tags.delete({
    groupId: "topics",
    ids: [
        "109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c",
        "d59eddbe-cb9f-51ab-9d22-532f63cd7893"
    ]
});
```

Delete a tag by its id and replace any references to the deleted tag with another tag that belongs to the same tag group

TypeScript

```
await client.tags.delete(
    "109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c",
    "c4cc205f-d543-55c7-8f1a-7490275be437"
);
```

Delete multiple tags from a specific tag group by their ids and replace any references to those deleted tags with another tag that belongs to the same tag group

TypeScript

```
await client.tags.delete({
    groupId: "topics",
    ids: [
        "109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c",
        "d59eddbe-cb9f-51ab-9d22-532f63cd7893"
    ]
}, "c4cc205f-d543-55c7-8f1a-7490275be437");
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Examples](#examples)