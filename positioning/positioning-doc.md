# Positioning

The css `position` property allow us to control how a page looks by changing the position of html elements. It'll also help you set how our html behaves respective to each other.

## z-index

[Understanding Stacking Context](../stacking-context/what.md)

The `z-index` property set where an element and its descendants will be located along the z-axis.
When elements overlaps, by default the arrangement will be defined by the stack, but with z-index property you can specify a different stacking order which will determined which one covers the other, greater values will cover elements with lower values. 
Z-index property will only work with positioned elements (positioned elements are those whose position is absolute, relative, or fixed).

### Info
__Demo__: http://codepen.io/llewan/pen/VLbeqv   
__Gist__: https://gist.github.com/anonymous/3d4f98b69c814a4d38e9

#### Credits

Leonardo Lewandowski - <l.lewandowski@globant.com>
