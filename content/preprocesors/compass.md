## Compass

Compass is a framework built with SASS which provides a bunch of mixins and helpers to save work.
It has many good features and lots of handy CSS workaround available to use but I'll point a few of them that sold me immediately.

### Why is useful?
Compass makes CSS3 really easy to use, it has also great built-in mixins to use Flexbox in a simpler way besides the utilities for common styling patterns.   
Also saying that Compass has very good documentation.

### Compass features
Among all the good features the framework count on, I think CSS3 mixins, Vertical Rhythm and handling URL assets and sprites are really good approaches to keep in mind.
 
#### CSS3 Mixins
CSS3 mixins are really useful and easy to use:   
First, you must import the file that handle CSS3 mixins at the top of the doc `@import "compass/css3"`
Then set some default values for the text-shadows:  

```
$default-text-shadow-color: rgba(red, 0.6);
$default-text-shadow-blur: 3px;
$default-text-shadow-v-offset: 1px;
```

and then.. 

```
<div class="shadow">this text has a shadow</div>

.shadow {
	@include single-text-shadow;
}
```

`@include single-text-shadow` will use defaults values. The final css output will be:

```
.shadow {
  text-shadow: 0px 1px 3px rgba(255, 0, 0, 0.6);
}
```


#### Mixins to Vertical Rhythm
`Vertical rhythm` on a Web involves manipulate CSS properties like font-size, line-height, padding, margins and borders and do many calculation that can become hard to maintain.  
Luckily, Compass has a great vertical rhythm module that helps clears this up.

For example:

```
@import "compass/typography/vertical_rhythm";
 
$base-font-size: 16px;
$base-line-height: 24px;
@include establish-baseline; 
```

These are the values that Vertical rhythm will use for the calculation and will be the base on witch the entire stylesheet calculates margins and paddings.  
And then when we need to change something like font sizes, we can keep everything aligned, just doing:

```
h1 {
  @include adjust-font-size-to(36px);
}
```


#### Mixins to handle assets url
Another useful feature of compass are the helper functions to handle url assets. Some frameworks use to precompile assets (stylesheets, images and javascript files) and send them through a pipeline, producing url issues, for example when calling an image from a sass partial `background: url(../../image1.png);`.     
To fix this we can just use `image-url` mixin on `background: image-url("image1.png");` and depending on the framework it will go to the URL previously defined on http_images_path.  
  

#### Mixins to handle sprites
There are useful tools for working with sprites that we can use, for example if we set a sprite sheet folder with many icons images, Compass can take care of them and assemble in a final image.  
After that it will create a number of custom mixins to make it easy to access the sprites in your project.

#### Credits

Leonardo Lewandowski - l.lewandowski@globant.com


 
