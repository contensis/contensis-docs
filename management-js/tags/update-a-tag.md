## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Management API](/help-and-docs/apis/management-js)
4.  Tags

[Log in to add to favourites](/account/login)

Page last updated 02 July 2025

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)

Update an existing tag. The update will be applied wherever this tag is used.

## Call signature

TypeScript

```
update(tag: IUpdateTag): Promise<Tag>;
```

## Parameters

Name

Type

Description

tag

[`IUpdateTag`](/help-and-docs/apis/management-js/model/tag)

A tag-like object containing the minimum required fields to update a tag (`id`, `groupId`, `value` and one `label`)

## Returns

A Promise that will resolve with the updated [Tag](/help-and-docs/apis/management-js/model/tag)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Example

Update the value and label of an existing tag

TypeScript

```
const tag = await client.tags.update({
    id: "109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c",
    groupId: "topics",
    value: "publications",
    label: { "en-GB": "Publications" }
});

console.log(`Successfully updated tag to version ${tag.version.versionNo}`);
```

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)