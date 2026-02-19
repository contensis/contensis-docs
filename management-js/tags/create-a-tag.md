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

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)

Create a new tag in a tag group

## Call signature

TypeScript

```
create(tag: ICreateTag): Promise<Tag>;
```

## Parameters

Name

Type

Description

tag

[`ICreateTag`](https://www.contensis.com/help-and-docs/apis/management-js/model/tag)

A tag-like object containing the minimum required fields to create a tag (`groupId`, `value` and one `label`)

## Returns

A Promise that will resolve with a created [Tag](https://www.contensis.com/help-and-docs/apis/management-js/model/tag)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Example

Create a new tag in a specific group with the minumum required fields

TypeScript

```
const tag = await client.tags.create({
    groupId: "topics",
    value: "books",
    label: { "en-GB": "Books" }
});

console.log(`Successfully created tag`);
```

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)