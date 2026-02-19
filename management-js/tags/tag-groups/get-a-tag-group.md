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

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)

Get a tag group by its id

## Call signature

TypeScript

```
get(id: string): Promise<TagGroup>;
```

## Parameters

Name

Type

Description

id

`string`

The tag group identifier

## Returns

A Promise that will resolve with a [Tag Group](https://www.contensis.com/help-and-docs/apis/management-js/model/tag-group)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Example

Get a tag group by its API id

TypeScript

```
const tagGroup = await client.tags.groups.get("topics");
```

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)