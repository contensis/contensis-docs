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

Create a new tag group

## Call signature

TypeScript

```
create(tagGroup: ICreateTagGroup): Promise<TagGroup>;
```

## Parameters

Name

Type

Description

tagGroup

[`ICreateTagGroup`](/help-and-docs/apis/management-js/model/tag-group)

A tag group-like object containing the required fields to create a tag group (`id`, `name` and an optional `description`)

## Returns

A Promise that will resolve with a created [Tag Group](/help-and-docs/apis/management-js/model/tag-group)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Example

Create a new tag group

TypeScript

```
const tagGroup = await client.tags.groups.create({
    id: "topics",
    name: "Topics",
    description: "A collection of topic tags"
});

console.log(`Successfully created tag group`);
```

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)