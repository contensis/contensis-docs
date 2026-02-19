1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [Image API](https://www.contensis.com/help-and-docs/apis/image-api)
4.  Introduction

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 28 February 2023

## What is caching?

Caching is the process of saving resources such as images, stylesheets and JavaScript and other site assets temporarily, so a browser or application doesn't need to download them each time.

When visiting a website for the first time, your browser retains information that helps your device access that website more efficiently during subsequent visits.

### More information

-   [Caching explained](https://cachingexplained.com/) provides a great primer into caching.
-   [Google Developers portal](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching#defining_optimal_cache-control_policy) provides a richer technical overview of HTTP caching.

## Problem with caching

Sometimes caching can be too aggressive which results in changes made to resources not being visible to the browser. This can be especially frustrating when replacing images to make a visual change. In order to avoid these issues the amount of time a resource is cached needs to be considered carefully and cache busting techniques need to be in place.

## Standard image cache - 1 day

Images accessed from Contensis outside of the Delivery API are returned with a [cache-control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control) header with a `max-age` of `86400`.

HTTP

```
Cache-Control: public, max-age of 86400 
```

This [directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control#Directives) allows us to tell the browser how long it should keep file in the cache since the first load. For example, `max-age=86400` indicates that the response can be cached and kept in the cache for one day.

With this policy, the browser completely skips the process of making requests to your server and opens files very fast. Any subsequent changes to the file in the 24 hour period will not be visible due to the cache control.

## Image caching in the Delivery API - 1 year

When requesting an image through the Delivery API we add a unique hash to the filename of the image. Please refer to the [fundamentals](https://www.contensis.com/help-and-docs/apis/image-api/introduction/fundamentals "fundamentals") page to see a full JSON example.

HTTP

```
/image-library/example-image.x3897116b.jpg
```

This hash updates when the source image is changed and therefore the resource can be cached for a long period of time. In our case we set a cache-control header of `max-age=31536000`

HTTP

```
Cache-Control: public, max-age of 31536000
```

This means all images with a hash in their filename are cached publicly (e.g. by browsers and proxy servers) for a period of 12 months.

## Invalidation key

If you choose to reference images outside of the Delivery API context we have an additional query string parameter that enables you to set a one year cache-control header. Simply append the `invalidationKey` parameter to the image URL e.g. `/images/example.jpg?invalidationkey=1.0`. If you are using this method then you must ensure you update the `invalidationkey` when the source image changes.

## Caching of images referenced in static files

If you want benefit from the caching of images referenced in CSS/JS files you'll need to roll your own cache busting. You can use either the hash method or the `invalidationkey` query string parameter.

The format of the the hash we use is:

The letter x followed by 8 hexadecimal characters (e.g. 0-9 and a-f) e.g. `x3897116b`

If you are using a build tool such as gulp you can use an NPM package like [gulp-filehash](https://www.npmjs.com/package/gulp-filehash) that can be templated to the same format that we use.