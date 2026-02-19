1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [Image API](https://www.contensis.com/help-and-docs/apis/image-api)
4.  Introduction

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 July 2022

Transformations can be combined together to apply multiple changes to an image as part of a single delivery request, e.g. crop an image and then apply a grayscale image effect. In certain cases you may want to perform additional transformations on the result of another transformation request. In order to do that, you can chain the transformations together using an `&` ampersand character.

The order of the query string parameters is important, each transformation is applied in sequence. The only exception is quality, which is always applied at the end.

Internally, the final output of the transformed image requires a quality level to be provided. If no quality level is specified, the Image API will automatically apply a default which balances between reducing image size and maintaining image quality. In some cases these defaults are not going to be perfect and you may find that you need to specify your own quality setting. That is more likely to be the case if the source image is not high quality, such as when the source image has already been pre-optimised for the web. For reference, the quality defaults are:

-   Jpeg: 75
-   Png: 60
-   Webp: 80

To get the best results from the Image API in terms of size reduction and quality you should use high-quality images as the Image API can handle images up to 25MB in size. In general, it is always worth carrying out a short experiment with some representative images from any collection of images that will share the same transformation parameters. You can then ensure that you have achieved an acceptable balance between image size and quality.

## Width

-   **Standard**
-   **Short**

![](https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=500)

---

## Width and quality

In this example, the image is resized to a width of 500px, before the quality is reduced.

-   **Standard**
-   **Short**

![](https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=500&q=50)

---

## Width, quality and grayscale effect

In this example, the image is resized to a width of 500px, before the quality is reduced and then the grayscale effect is applied.

-   **Standard**
-   **Short**

![](https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=500&q=50&e=grayscale)

## Repeating transformations

In this example the original image is scaled to 500px, rotated 180°, converted to black and white, rotated by a further 45° (resulting in the background being added), then resized to 200px wide.

-   **Standard**