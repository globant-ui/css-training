# What is stacking context

A stacking context is a group of elements with a common parent that react together to some property.

Every stacking context has a single HTML element as its root element. When a new stacking context is formed on an element, that stacking context confines all of its child elements to a particular place in the stacking order. That means that if an element is contained in a stacking context at the bottom of the stacking order, there is no way to get it to appear in front of another element in a different stacking context that is higher in the stacking order, even with a z-index of a billion!

## Which elements create a new stacking context

* the root element (HTML)
* positioned (absolutely or relatively) with a z-index value other than "auto"
* a flex item with a z-index value other than "auto"
* elements with an opacity value less than 1. (See the specification for opacity)
* elements with a transform value other than "none"
* elements with a mix-blend-mode value other than "normal"
* elements with a filter value other than "none"
* elements with isolation set to "isolate"
* on mobile WebKit and Chrome 22+, position: fixed always creates a new stacking context, even when z-index is "auto" (See this post)
* specifing any attribute above in will-change even you don't write themselves directly (See this post)
elements with -webkit-overflow-scrolling set to "touch"

## Let's see it with some examples

**Stacking context on opacity**

__Demo__: http://codepen.io/asainz/pen/YXGQJW  
__Gist__: https://gist.github.com/asainz/d45f64b7637c043c66b0  

What's happening here? How does stacking context affect opacity? The parent's opacity , in a way, limits how opaque the child can be. It simplifies the process to think opacity as percentages:  

A child with `opacity: 1` will be 100% opaque. A child with `opacity:.5` will be 50% opaque (or 50% dimmed). But, the important part is: opaque/dimmed relative to what? **Relative to its parent. That's the stacking context in action**

A child will get as opaque/dimmed as its parent allows it. If a `div` has is `opacity:.5` and its child is `opacity:1`, the child itself will be totally opaque, but its parent is half opaque, so 50% is as opaque as the child will get. It can't be more that 50%, because it cant't escape its stacking context.

**Stacking context on z-index**

__Demo__: http://codepen.io/asainz/pen/XbjapJ  
__Gist__: https://gist.github.com/asainz/e3fe53972f24e46e39df  

In this case, the stacking context works in the same way as in the previous example. The child will only get as high as its parent allows it.

If you have two sibling divs, one `z-index: 1` and the other `z-index:2`, none of the first `div` children will be on top of the second `div`, no matter what z-index they have. That's because the stacing context of the first `div` has a lower `z-index` than the second one, so the children stacking contexts can't surpass that.

**Stacking context on transform**

__Demo__: http://codepen.io/asainz/pen/EjgvGN  
__Gist__: https://gist.github.com/asainz/88de386807d59da0d9e7  

First of all, a bit of theory:

> Any computed value other than none for the transform results in the creation of both a stacking context and a containing block. The object acts as a containing block for fixed positioned descendants.  

> Any positioned (absolutely or relatively) with a z-index value other than "auto" results in the creation of a stacking context.

There are a couple of things happening in these examples. Let's go through all of them:

> For these examples, we won't be including the `html` stacking context.

`#block1` has only 1 new stacking context and it's created on `span.below` since it's relatively positioned and it has a `z-index` other than `auto`. This means that the `.overlay` (the DOM element, remember it doesn't have its own stacking context) and the `span.below` stacking context are inside the same stacking context (`html` element), so `span.below` can be placed below `.overlay`.

`#block2` has 2 new stacking context: one it's created on `.animated`, since it has a `transform` property other than `none` and the other one it's created on `span.below` (the same as the previous example). This means that the `span.below` stacking context will be inside the `.overlay`stacking context (because it's inside in the DOM) so the `span.below` stacking context will **never** be able to be placed below the `.overlay`stacking context.

`#block3` has 2 new stacking context: one it's created on `animated` since it has a `transform` property other than `none` and the other one it's **also** created on `span.below` since it's relatively positioned and it has a `z-index` other than `auto`. But, since both new stacking context and the `.overlay` element belong to the same stacking context (`html` element), they can placed below it.

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
