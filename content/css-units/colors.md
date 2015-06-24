# Colors

The color CSS data type denotes a color in the sRGB color space (RED, GREEN, and BLUE light).

Associated with the color in the sRGB space, a value also consists of an alpha-channel coordinate, transparency value, indicating how the color should composite with its background color.


## Color methods

### Hexadecimal Colors

Hexadecimal color values are supported in all major browsers.

A hexadecimal color is specified with: #RRGGBB, where the RR (red), GG (green) and BB (blue) hexadecimal integers specify the components of the color. All values must be between 00 and FF.

Example:

```css
 .bg-color {
 	background-color: #ff0000;
 }   /* red */

```
### RGB Colors

RGB color values are supported in all major browsers.

An RGB color value is specified with: rgb(red, green, blue). Each parameter (red, green, and blue) defines the intensity of the color and can be an integer between 0 and 255 or a percentage value (from 0% to 100%).

Example:

```css
 .bg-color {
 	background-color: rgb(0, 0, 255);
 }   /* blue */

```


### RGBA Colors

RGBA color values are supported in IE9+, Firefox 3+, Chrome, Safari, and in Opera 10+.

RGBA color values are an extension of RGB color values with an alpha channel - which specifies the opacity of the object.

Example:

```css
 .bg-color {
 	background-color: rgb(255, 0, 0, 0.3);
 }   /* red with opacity of 0.3 */

```
Note: The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (fully opaque).


### HSL Colors

HSL color values are supported in IE9+, Firefox, Chrome, Safari, and in Opera 10+.

HSL stands for hue, saturation, and lightness - and represents a cylindrical-coordinate representation of colors.

An HSL color value is specified with: hsl(hue, saturation, lightness).

Hue is a degree on the color wheel (from 0 to 360) - 0 (or 360) is red, 120 is green, 240 is blue. Saturation is a percentage value; 0% means a shade of gray and 100% is the full color. Lightness is also a percentage; 0% is black, 100% is white.

Example:

```css
 .bg-color {
 	background-color: hsl(120, 100%, 50%);
 }   /* green */

```

### HSLA Colors

HSLA color values are supported in IE9+, Firefox 3+, Chrome, Safari, and in Opera 10+.

HSLA color values are an extension of HSL color values with an alpha channel - which specifies the opacity of the object.

An HSLA color value is specified with: hsla(hue, saturation, lightness, alpha), where the alpha parameter defines the opacity.

```css
 .bg-color {
 	background-color: hsl(120, 100%, 50%, 0.3);
 }   /* green with opacity*/

```
Note: The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (fully opaque).

### Color Names

All modern browsers support the following 140 color names. These are the basic color keyword:

- Black	
- Silver	
- Gray	
- White	
- Maroon	
- Red	
- Purple	
- Fuchsia	
- Green	
- Lime	
- Olive	
- Yellow	
- Navy	
- Blue	
- Teal	
- Aqua

Example:

```css
 .bg-color {
 	background-color: aqua;
 } 

```
Note: The library colors.css is a collection of skin classes to use while prototyping in the browser.All the information related could be find here:
[colors.csss](http://clrs.cc/)

### Considerations about the color use

#### Hexadecimal Colors 

Is very attractive because it’s short and simple to remember and type out. But HEX might not work for you in all situations, which is when you may wish to consider one of the other two methods. Both of which have their pluses and minuses.

#### RGBA Colors 

RGBA is well-known and supported in older versions of Internet Explorer (9 and older). It has an additional field for alpha values which come in handy when you want to work with opacity.

#### HSLA Colors 

HSLa is a newer, more intuitive way to work with colors. Unlike RGBA where we have to mesh some numbers around to get the color we want, we can grab the Hue then work with percentages to get the saturation and lightness levels that we need. HSLa also includes an alpha value for opacity.

#### Info

__Demo__: http://codepen.io/mvargas21/pen/mJqxzw
__Gist__: https://gist.github.com/souichi6666/1e2375ee1374a4a1bfa1

#### Credits

Mauricio Garcia Vargas - <mauricio.garcia@globant.com> 
