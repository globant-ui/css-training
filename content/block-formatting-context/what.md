# What is block formatting context

A block formatting context is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with each other.

## Which elements create a new block formatting context

* the root element or something that contains it
* elements where float is not none
* elements where position is absolute or fixed
* elements with display: inline-block
* elements with display: table-cell, which is the default for HTML table cells
* elements with display: table-caption, which is the default for HTML table captions
* elements where overflow has a value other than visible
* elements with display: flex or inline-flex

## Why are they important?

**A block formatting context contains everything inside of the element creating it that is not also inside a descendant element that creates a new block formatting context.**

Block formatting contexts are important for the positioning and clearing of floats. The rules for positioning and clearing of floats apply only to things within the same block formatting context. Floats do not affect the layout of things in other block formatting contexts, and clear only clears past floats in the same block formatting context.