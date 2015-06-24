# Flexbox

## What is it?

The flexbox is a new layout mode. It is great when the page layout must accommodate different screen sizes and different display devices.

Child elements in a flexbox can be laid out in any direction and can have flexible dimensions to adapt to the display space. Positioning child elements is thus much easier, and complex layouts can be achieved more simply and with cleaner code, as the display order of the elements is independent of their order in the source code. This independence intentionally affects only the visual rendering, leaving speech order and navigation based on the source order.

## Flexible boxes concept

The defining aspect of the flex layout is the ability to alter its items' width and/or height to best fill the available space on any display device. A flex container expands items to fill available free space, or shrinks them to prevent overflow.

The flexbox layout algorithm is direction-agnostic as opposed to the block layout, which is vertically-biased, or the inline layout, which is horizontally-biased. While the block layout works well for pages, it lacks sufficient definition to support application components that have to change orientation, resize, stretch, or shrink as the user agent changes, flips from vertical to horizontal, and so forth.

## Flexbox vocabulary

The flex layout is based on `flex-flow directions`. You can take a look at this image from the W3C specs

![flexbox specs](https://cdn.css-tricks.com/wp-content/uploads/2011/08/flexbox.png "Flexbox vocabulary")

The items will be laid out following either the main axis (from main-start to main-end) or the cross axis (from cross-start to cross-end).

1. `main axis` The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the flex-direction property (see below).
2. `main-start | main-end` The flex items are placed within the container starting from main-start and going to main-end.
3. `main size` A flex item's width or height, whichever is in the main dimension, is the item's main size. The flex item's main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
4. `cross axis` The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
5. `cross-start | cross-end` Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
6. `cross size` The width or height of a flex item, whichever is in the cross dimension, is the item's cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.



## Flexbox properties

There are several new properties introduced by flexbox. Some of them affect the parent element and some of them its children.

**Parent flexbox properties**

1. [display](#display)
2. [flex-direction](#flex-direction)
3. [flex-wrap](#flex-wrap)
4. [flex-flow](#flex-flow)
5. [justify-content](#justify-content)
6. [align-items](#align-items)
7. [align-content](#align-content)

**Children flexbox properties**

1. [order](#order)
2. [flex-grow](#flex-grow)
3. [flex-shrink](#flex-shrink)
4. [flex-basis](#flex-basis)
5. [flex](#flex)
6. [align-flex](#align-flex)

### Parent flexbox properties

#### display

It enables flexbox in the element. 

```css
/* possible values */

.flex {
    display: flex;
}

.flex {
    display: inline-flex;
}
```

__Demo__: http://codepen.io/asainz/pen/zGPKOv  
__Gist__: https://gist.github.com/asainz/79f3771b97ec05828686  


#### flex-direction

This establishes the main-axis. This means, which direction the children items will follow (horizontal or vertical).

```css
.flex{
    flex-direction: row; /* default */
}

.flex{
    flex-direction: row-reverse;
}

.flex{
    flex-direction: column;
}

.flex{
    flex-direction: column-reverse;
}
```

__Demo__: http://codepen.io/asainz/pen/BNmLQG  
__Gist__: https://gist.github.com/asainz/6be47ef9f134978275a9  

#### flex-wrap

Flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

```css
.flex{
    flex-wrap:  nowrap; /* default */
}

.flex{
    flex-wrap: wrap;
}

.flex{
    flex-wrap: wrap-reverse;
}
```

__Demo__: http://codepen.io/asainz/pen/doZpWZ  
__Gist__: https://gist.github.com/asainz/bbb5e721f37e84c19965  

#### flex-flow

Shorthand for `flex-direction` and `flex-wrap`.

```css
.flex{
    flex-flow: row nowrap;
}

.flex{
    flex-flow: ANY_DIRECTION_OPTION ANY_WRAP_OPTION;
}
```

#### justify-content

This defines the alignment along the main axis (flex-direction value). It helps distribute extra free space.

```css
.flex{
    justify-content: flex-start; /* default */
}

.flex{
    justify-content: flex-end;
}

.flex{
    justify-content: center;
}

.flex{
    justify-content: space-between;
}

.flex{
    justify-content: space-around;
}
```

__Demo__: http://codepen.io/asainz/pen/VLrKEd  
__Gist__: https://gist.github.com/asainz/52cdb17f79092d924fe8  

#### align-items

This defines the default behaviour for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross-axis (perpendicular to the main-axis or flex-direction value)

```css
.flex{
    align-items: flex-start; /* default */
}

.flex{
    align-items: flex-end;
}

.flex{
    align-items: center;
}

.flex{
    align-items: baseline;
}

.flex{
    align-items: stretch;
}
```

__Demo__: http://codepen.io/asainz/pen/bdYwZb
__Gist__: https://gist.github.com/asainz/23c61da77ac38332d32c


#### align-content

This aligns a flex container's lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.

This property has no effect when there is only one line of flex items.

```css
.flex{
    align-content: flex-start;
}

.flex{
    align-content: flex-end;
}

.flex{
    align-content: center;
}

.flex{
    align-content: space-between;
}

.flex{
    align-content: space-around;
}

.flex{
    align-content: stretch; /* default */
}
```

__Demo__: http://codepen.io/asainz/pen/zGPoYP  
__Gist__: https://gist.github.com/asainz/0e52b9953df313b4e28d  

### Children flexbox properties

#### order

It changes the order the elemnts are rendered. By default, they are rendered in the order defined in the DOM

```css
.item{
    order: NUMBER;
}
```

__Demo__: http://codepen.io/asainz/pen/VLrmzN  
__Gist__: https://gist.github.com/asainz/75e6ec316b83f45e4884

#### flex-grow

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, every child will set to an equal size inside the container. If you were to give one of the children a value of 2, that child would take up twice as much space as the others. Negatives number are invalid.

```css
.item{
    flew-grow: NUMBER; /* defult to 1 */
}
```

__Demo__: http://codepen.io/asainz/pen/VLrmzN  
__Gist__: https://gist.github.com/asainz/75e6ec316b83f45e4884

#### flex-basis

This defines the default size of an element before the remaining space is distributed. The main-size value makes it match the width or height, depending on which is relevant based on the flex-direction.

```css
.item {
  flex-basis: LENGTH | auto; /* default auto */
}
```

For instance

```css
.flex.first-example p:first-child { 
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 20em;
}
.flex.first-example p:last-child { 
    flex-grow: 2;
    flex-shrink: 2;
    flex-basis: 20em;
} 
```

Both flex items want to be 20em wide. Because of the flex-grow, if the flex container is larger than 40em, the 2nd child will take twice as much leftover space as the first child.

If `flex-basis` is set to 0, the extra space around content isn't factored in. If set to auto, the extra space is distributed based on it's flex-grow value

__Demo__: http://codepen.io/asainz/pen/XbzpOW  
__Gist__: https://gist.github.com/asainz/1ab76be1ff4cb9dc0c7e

#### flex-shrink

This defines the ability for a flex item to shrink if necessary. Negatives number are invalid. Think of it as the opposite of `flex-grow`. When there is no space to accommodate all the items based on their `flex-grow` and `flex-basis` values, `flex-shrink` indicates how much an item will be reduced. If we have to items, and the first one has `flex-shrink: 1` and the last one has `flex-shrink: 2`, the lat one will be reduced twice as much as the first one.

```css
.item{
    flex-shrink: NUMBER; /* defult to 1 */
}
```

__Demo__: http://codepen.io/asainz/pen/RPjKBV  
__Gist__: https://gist.github.com/aac145b936b3a9274236

#### flex

Shorthand for `flex-grow`, `flex-shrink` and `flex-basis`

```css
.flex{
    flex-flow: 0 1 auto; /* default */
}

.flex{
    flex-flow: NUMBER NUMBER [LENGTH | auto];
}
```

#### align-self

Allows to override the alignment set by `align-items` for an individual item.

```css
.flex{
    align-self: flex-start; /* default */
}

.flex{
    align-self: flex-end;
}

.flex{
    align-self: center;
}

.flex{
    align-self: baseline;
}

.flex{
    align-self: stretch;
}
```

__Demo__: http://codepen.io/asainz/pen/LVOyLX  
__Gist__: https://gist.github.com/07695f9140ca9a15e14e