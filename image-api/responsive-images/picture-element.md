Using different images or the same image that have been cropped to fit a particular screen's features can help in communicating a message effectively.

HTML

```
<picture>
      <!-- Show a portrait cropped version of the image in grayscale for viewports up to 320px -->
      <source media="(max-width: 320px)" 
              srcset="https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=240&h=320&fit=crop&e=grayscale 240w">

      <!-- Show a portrait cropped version of the image for viewports up to 480px -->
      <source media="(max-width: 480px)" 
              srcset="https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=240&h=320&fit=crop 240w">

      <!-- Show a traditional 4:3 crop of the image for viewports up to 640px -->
      <source media="(max-width: 640px)" 
              srcset="https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=640&h=320&fit=crop 640w">

      <!-- Show a letterbox crop of the image for viewports up to 1920px -->
      <source media="(max-width: 1920px)" 
              srcset="https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=1024&h=450&fit=crop-bottom 1024w">

      <!-- Show a tighter letterbox crop of the image for viewports larger than 1921px -->
      <source media="(min-width: 1921px)" 
              srcset="https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=1920&h=600&fit=crop 1920w">

      <img src="https://www.contensis.com/image-library/resources-images/image-api-examples/tree-frog.jpg?w=240&h=320&fit=crop" 
           alt="Dainty tree frog">
</picture>
```