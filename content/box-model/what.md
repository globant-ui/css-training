# Box model

## What is it?

In a document, each element is represented as a rectangular box. The box model is the way each of these boxes are described in CSS. This model describes the content of the space taken by an element. Each box has four edges: the margin edge, border edge, padding edge, and content edge.

You can see a graphic representation of the box model here: [http://codepen.io/asainz/pen/ogwXJR](http://codepen.io/asainz/pen/ogwXJR)

### Content area

It's the actual content of the element.

### Padding area

The padding area wraps the content area. If the content are has a background, it will extend to the padding area. Any content will not extend to the padding area.

### Border area

The border area extends the padding area to the border edge.

### Margin area

The margin area extends the border area with an empty area used to separate the element from its neighbors.

## Different types of box model

CSS3 brought a new `box-sizing` property that allows you to alter how the box model is calculated. The `box-sizing` has the following possible values. Check this codepen [http://codepen.io/asainz/pen/LELEvd](http://codepen.io/asainz/pen/LELEvd) to see how boxes are affected by the different values.

### content-box

This is the default style as specified by the CSS standard. The width and height properties are measured including only the content, but not the padding, border or margin.

### border-box

The width and height properties include the padding and border, but not the margin. 

## Examples

1. Box model representation

__Demo__: http://codepen.io/asainz/pen/ogwXJR  
__Gist__: https://gist.github.com/asainz/5e44e9f3c8cd2316f738

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
