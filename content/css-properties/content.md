# Content

This CSS property allow to insert generated content.

It is used with the ::before and ::after pseudo-elements to generate content in an element. Objects inserted using the content property are anonymous replaced elements (In CSS, a replaced element is an element whose representation is outside the scope of CSS).




## All content values

| Value |Description |
| ------------- | ----------- |
| normal  | Default value. Sets the content, if specified, to normal, which default is "none" (which is nothing)|
| none  | Sets the content, if specified, to nothing |
| counter	|Sets the content as a counter	|
|attr(attribute)| Sets the content as one of the selector's attribute|
|string  | Sets the content to the text you specify|
|open-quote  |  Sets the content to be an opening quote |
|close-quote  |  Sets the content to be a closing quote |
|no-open-quote  |  Removes the opening quote from the content, if specified|
|no-close-quote  |  Removes the closing quote from the content, if specified|
|url(url) |  Sets the content to be some kind of media (an image, a sound, a video, etc.)|
|initial | Sets this property to its default value. Read about initial|
|inherits |Inherits this property from its parent element. Read about inherit|



## Code example

```css

.class-name(or element):before{
 	content:value;
 }
 
 .class-name(or element):after{
 	content:value;
 }

```
    
## Info

__Demo__: http://codepen.io/mvargas21/pen/GJOaEb

__Gist__: https://gist.github.com/souichi6666/ed3963421456d8cf9219


## Credits

Mauricio Garcia Vargas - mauricio.garcia@globant.com