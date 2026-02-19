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

Delete an existing tag group by its id

## Call signature

TypeScript

```
delete(id: string): Promise<void>;
```

## Parameters

Name

Type

Description

id

`string`

The API id of the tag group to delete

## Returns

A Promise that will resolve with no data

## Remarks

A tag group cannot be deleted if it contains any tags

Throws any error that is returned by the API for any unsuccessful request echoing the HTTP status returned from the API

## Example

Delete an unused tag group by its id

TypeScript

```
await client.tags.groups.delete("topics");
```

## On this page

-   [Call signature](#call-signature)
-   [Parameters](#parameters)
-   [Returns](#returns)
-   [Remarks](#remarks)
-   [Example](#example)