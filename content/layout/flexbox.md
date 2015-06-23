# Flexbox

## What is it?

The flexbox is a new layout mode. It is great when the page layout must accommodate different screen sizes and different display devices.

Child elements in a flexbox can be laid out in any direction and can have flexible dimensions to adapt to the display space. Positioning child elements is thus much easier, and complex layouts can be achieved more simply and with cleaner code, as the display order of the elements is independent of their order in the source code. This independence intentionally affects only the visual rendering, leaving speech order and navigation based on the source order.

## Flexible boxes concept

The defining aspect of the flex layout is the ability to alter its items' width and/or height to best fill the available space on any display device. A flex container expands items to fill available free space, or shrinks them to prevent overflow.

The flexbox layout algorithm is direction-agnostic as opposed to the block layout, which is vertically-biased, or the inline layout, which is horizontally-biased. While the block layout works well for pages, it lacks sufficient definition to support application components that have to change orientation, resize, stretch, or shrink as the user agent changes, flips from vertical to horizontal, and so forth.

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

Shorthand for flex-direction and flex-wrap.

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

