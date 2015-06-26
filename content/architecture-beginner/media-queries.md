## Media Queries
 
### What is a Media Query?
Sometimes we need to change styles based on the characteristics of the device, so we can use media queries to look at the capability of the device, like width or height of the browser, orientation and resolution.

Media Queries are really useful for building a responsive grid. We can add breakpoints where parts of the design will behave differently.
  
A Media query can contain one or more expressions, which resolve to either true or false.  
An example for the syntax:

```
@media screen and (max-width: 300px) {
    body {
        background-color: red;
    }
}
```

The background-color is red when the width of this document is less than 300px.
Noticed that we use the `and` operator, but you can also use `only` and `not` operators.
  
```
@media not all and (monochrome) { ... } 
```

or
 
```
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) {
} 
```

Noticed that in the expressions of the previous examples we use `min-device-width` or `max-width` to describe the requirements of the device, these are called media features.
In fact, media features here are `device-width` and `max-width` and there others like `color`, `aspect-ratio`, `orientation`. And they are usually prefixed with "min-" or "max-" in order to express "greater than" or "less than" and avoid using "<" and ">" symbols, which would conflict with HTML.

#### Info
__Demo__: http://codepen.io/llewan/pen/JdMYEQ  
__Gist__: https://gist.github.com/anonymous/95081cf9f1a9535122a0


#### Credits

Leonardo Lewandowski - l.lewandowski@globant.com
