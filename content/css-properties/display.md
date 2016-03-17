# Display

Think of every element in the DOM as a rectangular box. This property lets you specify the type of box used to render an element and how it behaves.

## Common display properties

### none

Probably the most basic and easier to understand. The none value will completly shut off the element display. It'll also apply the same value to al it's descendants meaning that the element and its descendant will not be rendered.

Do not confuse `display: none` with `visibility: hidden`. The last one will render the box's dimensions (it means, it will occupy space in the DOM).

### inline

The default display value, it will not affect the flow of the elements in any way. An inline element is affected by margin and padding, but it'll only push the content away horizontally. It's not affected by width or height.

### block

Another common value, a block element will start from a new line and take as much horizontal space as it possibly can.

### inline-block

Much like a inline element, but it is affected by width and height.

### table and table-cell

this values exist mainly to force elements other than table elements to behave as such.

#### Info

__Demo__: http://codepen.io/Vratyas/pen/doWYEw?editors=110  
__Gist__: https://gist.github.com/Vratyas/57d7c6b3f59eddffe529

#### Credits

Juan Fernandez - <j.fernandez@globant.com>
