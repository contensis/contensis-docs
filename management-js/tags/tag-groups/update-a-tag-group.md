## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Tags
5.  Tag groups

[Log in to add to favourites](/account/login)

Page last updated 02 July 2025

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)

Update an existing tag group

## Call signature

TypeScript

```
update(tagGroup: IUpdateTagGroup): Promise<TagGroup>;
```

## Parameters

Name

Type

Description

tagGroup

[`IUpdateTagGroup`](/help-and-docs/apis/management-js/model/tag-group)

A tag group-like object containing the required fields to update a tag group (`id`, `name` and an optional `description`)

## Returns

A Promise that will resolve with the updated [Tag Group](/help-and-docs/apis/management-js/model/tag-group)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Example

Update an existing tag group

TypeScript

```
const tagGroup = await client.tags.groups.update({
    id: "topics",
    name: "Topics / themes",
    description: "A collection of topic / theme tags"
});

console.log(`Successfully updated tag group to version ${tagGroup.version.versionNo}`);
```

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)