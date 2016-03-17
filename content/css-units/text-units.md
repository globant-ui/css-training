## CSS Units

We often need to set height, width, margin, or different sizes for images or text boxes. 
To do so CSS offers different units for expressing length. The units of measure are divided into two groups: Relative length units and absolute length units.

### Relative length units
Relative length units like `em` or `rem` are commonly used for typography and everything regarding to it, and are relative to another length property. 
`em` is relative to the font-size of the current element and `rem` is relative to the font-size of the root element.

`%` The percent unit is much like the `em` unit, except for a few fundamental differences. 
In the font-size property, percentage values are relative to the font size of the parent element, but in text-indent, margin, padding, and width properties, percentage values are relative to the width of the parent element.

### Absolute length units
Absolute length units represents a physical measurement and should be used only when the physical characteristics of the output medium are known, such as bitmap images or print layout.
The units of measurement are `cm` `mm` `in` `pt` `pc` and `px`. `px` defines a measurement in screen pixels.

#### Info
__Demo__: http://codepen.io/llewan/pen/Jdyapv
__Gist__: https://gist.github.com/anonymous/2c69b027a31ddbf0d7ba

#### Credits

Leonardo Lewandowski - l.lewandowski@globant.com
