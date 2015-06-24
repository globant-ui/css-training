# Overflow

The overflow property specifies whether to clip content, render scrollbars or just display content when it overflows its block level container.

Using the overflow property with a value different to visible (its default) will create a new block formatting context. This is technically necessary — if a float intersected with the scrolling element it would forcibly rewrap the content. The rewrap would happen after each scroll step, leading to a slow scrolling experience.

## Types of overflow

### Overflow-x

The overflow-x property specifies whether to clip content, render a scroll bar, or display overflow content of a block-level element, when it overflows at the left and right edges.

### Overflow-y

The overflow-y property specifies whether to clip content, render a scroll bar, or display overflow content of a block-level element, when it overflows at the top and bottom edges.

## All overflow values

| Name | description |
| -------------| ----------- |
|visible |  The overflow is not clipped. It renders outside the element's box. This is default   |
|hidden  | The overflow is clipped, and the rest of the content will be invisible|
|scroll	|The overflow is clipped, but a scroll-bar is added to see the rest of the content|
|auto| If overflow is clipped, a scroll-bar should be added to see the rest of the content|
|initial  | Sets this property to its default value.|
|inherit  | Inherits this property from its parent element.|

## Code syntaxis

```css
 {
  overflow:value; 
  // Values: visible|hidden|scroll|auto|initial|inherit;
  overflow-x:value; 
  // Values: visible|hidden|scroll|auto|initial|inherit;
  overflow-y:value; 
  // Values: visible|hidden|scroll|auto|initial|inherit;
}

```
#### Info

__Demo__: http://codepen.io/mvargas21/pen/xGXvrr 
__Gist__: https://gist.github.com/souichi6666/6f4d0a973b8ebbabef63

#### Credits

Mauricio Garcia Vargas - <mauricio.garcia@globant.com>
