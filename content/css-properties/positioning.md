# Positioning

## Types of positioning

The css `position` property allow us to control how a page looks by changing the position of html elements. It'll also help you set how our html behaves respective to each other. There are different types of position, and they all have different behavior.

* `static` is the default value of every element. An element positioned as static is not considered to be positioned at all.  
* `relative` behaves the same as a static positioned element, unless modified by top, left, bottom or right properties, relative to its original position in the flow. Relative positioning does not affect other elements in the layout as won't be adjusted to fill other element's space.  
* `fixed` behaves the same as a relative positioned element, but it'll be positioned relative the the viewport. So, even if you scroll the page, the element position will stay the same.  
* `absolute` behaves the same as a fixed element, but it'll be positioned relative to its nearest positioned ancestor (non static element) or the body, if it does not find any. Other elements will be adjusted to fill an absolute positioned element space, since absolute positioned elements are taken out of the normal flow and leaves an empty space.

The positioned elements are affected by another property, `z-index`, which is very important when we need to create a layout.

#### Info

__Demo__: http://codepen.io/Vratyas/pen/zGvLqv?editors=110  
__Gist__: https://gist.github.com/Vratyas/7a423f5fa5da1416b8d5  

## z-index

The `z-index` property set where an element and its descendants will be located along the z-axis.
When elements overlaps, by default the arrangement will be defined by the stack, but with z-index property you can specify a different stacking order which will determined which one covers the other, greater values will cover elements with lower values.
Z-index property will only work with positioned elements (positioned elements are those whose position is absolute, relative, or fixed).

`z-index` is also affected for context of the element where it's applied. Depending on where the element is placed in the DOM and also where its parent is, changing the `z-index` value will have different results. [You can read more in-depth info about the Stacking Context here.](../stacking-context/what.md)

#### Info
__Demo__: http://codepen.io/llewan/pen/VLbeqv  
__Gist__: https://gist.github.com/anonymous/3d4f98b69c814a4d38e9

## Credits

Juan Fernandez - <j.fernandez@globant.com>  
Leonardo Lewandowski - <l.lewandowski@globant.com>
