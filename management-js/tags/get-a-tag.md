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

Get a tag by its id or provide options to find a tag by its label

## Call signatures

TypeScript

```
get(id: string): Promise<Tag>;

get({
    groupId: string;
    label: string;
    language?: string;
}: TagGetByLabelOptions): Promise<Tag>;
```

## Parameters

Name

Type

Description

id

`string`

The tag GUID identifier

options

`TagGetByLabelOptions`

An options object to find a tag in a known tag group by its label and in a specific language

## Returns

A Promise that will resolve with a [Tag](https://www.contensis.com/help-and-docs/apis/management-js/model/tag)

## Remarks

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Examples

Get a tag by its GUID identifier

TypeScript

```
const tag = await client.tags.get("109eb3e9-98c9-5ab2-b9df-f1c80af3ac5c");
```

Get a tag from a specific tag group by its label and label's language

TypeScript

```
const tag = await client.tags.get({
    groupId: "topics",
    label: "Books",
    language: "en-GB"
});
```

## On this page

-   [Call signatures](#call-signatures)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Examples](#examples)