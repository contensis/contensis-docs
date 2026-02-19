The crop mode defines how the image should be scaled and aligned when the `fit=crop` parameter is set. The `width` and `height` parameters set both the crop dimensions and initial resize of the image. This crop mode ensures the image is always cropped to the exact dimensions specified, and results in some of the original image being cut off.

Valid values for the crop position are `top`, `bottom`, `left`, `right`. If no value is explicitly set, the default behavior is to crop from the center of the image.

---