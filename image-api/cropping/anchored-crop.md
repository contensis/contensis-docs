## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [Image API](https://www.contensis.com/help-and-docs/apis/image-api)
4.  Cropping

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 20 April 2023

Extract a region of the original image with a given width and height. You can specify the [anchor](#anchor) parameter to select which part of the image to extract, or use exact [coordinate cropping](https://www.contensis.com/help-and-docs/apis/image-api/cropping/exact-crop "exact-crop").

![Example crop area for exact crop](https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog-anchor-example.jpg?width=1000&quality=50)

The rectangle outlined in the image will be used for the crop, and is defined by the following parameters `crop=1500,1500,2300,1280`

## Crop the original image to 1500x1500px from the center

-   **Standard**
-   **Short**

![](https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?crop=1500,1500,c&width=485&quality=50)

---

## Crop the original image to 1500x1500px from the bottom left

-   **Standard**
-   **Short**

![](https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?crop=1500,1500,bl&width=485&quality=50)

## Anchor

Position

Standard

Short

Top

top

t

Top right

top-right

tr

Right

right

r

Bottom right

bottom-right

br

Bottom

bottom

b

Bottom left

bottom-left

bl

Left

left

l

Top left

top-left

tl

Center

center

c