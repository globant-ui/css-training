# What is the block formatting context

The block formatting context is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with each other.

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

**A block formatting context contains everything inside of the element creating the mentioned context that is not also inside a descendant element that creates a new block formatting context.**

Block formatting contexts are important for the positioning and clearing of floats. The rules for positioning and clearing of floats apply only to things within the same block formatting context. Floats do not affect the layout of things in other block formatting contexts, and clear only clears past floats in the same block formatting context.

## Some examples

#### clear only clears past floats in the same block formatting context

```html
<div class="container">
  <!-- <div id="clear-1" class="clear"></div> -->
  
  <div class="box float-left"></div>
  <div class="box float-left"></div>
  <div class="box float-left"></div>
  
  <div id="clear-2" class="clear"></div>
</div>
```

This means that if you implement the clearing like `#clear-2`, the container will be able to expand to its children height, since that div will clear the three floats. If you remove that div and uncomment `#clear-1` the container will collapse, since `#clear-1` can't clear floats that appear after itself.

__Demo__: http://codepen.io/asainz/pen/OVOQzy  
__Gist__: https://gist.github.com/asainz/9e7f6af9fb88627d4620  


#### floats do not affect the layout of things in other block formatting contexts

```html
<div class="container">
  <div class="box float-left"></div>
  <div class="box float-left"></div>
  <div class="box float-left"></div>
</div>
```

In this example, we are not applying any clearing, so the container will collapse. But, based on the docs, if we create a new block formatting context in the container, the float of its children will not affect it, since the floating will create yet another block. One way we can achieve that is setting the `overflow` value of the container to anything other that `visible`.

__Demo__: http://codepen.io/asainz/pen/WvXMYp  
__Gist__: https://gist.github.com/asainz/707accb65d33692faf33  