# Minimizing the browser reflow

`Reflow` is a process in which the web browser calculates the position of each element in the document. It is important to reduce to the minimum the number of reflows, since they will the user from doing anything while it is in process and it mobile devices this can reflect in a poor user experience.

A `repaint`, also known as `redraw`, is a process in which the web browser calculates and determines colors, visibility, borders and any other visual styles and then updates the screen.

## What actions force a reflow

* insert, remove or update an element in the DOM
* modify content on the page (text in an input)
* move an element
* animate an element
* take measurements of an element such as offsetHeight or getComputedStyle
* change a CSS style
* change the className of an element
* add or remove a stylesheet
* resize the window
* scroll

As you can see, almost everything forces a reflow, so we have to be cautious when dealing with dom elements

## How can i minimize the number of them?

* Avoid as much as possible using inline styles individually. These trigger a reflow for each dynamic style change. Use a class instead

This code will trigger 3 reflows, one for each property

```js
$('.box')
    .css('border', '1px solid tomato')
    .css('background', 'red')
    .css('font-size', '1.2em');
```


This code will trigger 1 reflow: triggered by adding a class

```css
.selected{
    border: 1px solid tomato;
    background: red;
    font-size: 1.2em;
}
```

```js
    $(.box).addClass('selected');
```

* Add or remove classes as low in the tree as possible. A reflow in an element will recalculate the position of all of its children.

* Cache values if you need to compute styles

For instance, just by asking the value `element.offsetHeight` the browser will make a reflow (since it's needed to get the actual value). The snippet below will trigger 5 reflows.

```js
var el = document.querySelector('.my-box');

if( el.offsetHeight <= 100 ){
    console.log('offset is <= 100');
}

if( el.offsetHeight > 100 && el.offsetHeight <= 500 ){
    console.log('offset is > 100 && <= 500');
}

if( el.offsetHeight > 500 && el.offsetHeight <= 1000 ){
    console.log('offset is > 500 && <= 1000');
}
```

Instead, use this. It will trigger only 1 reflow

```js
var el = document.querySelector('.my-box');
var offsetHeight = el.offsetHeight;

if( offsetHeight <= 100 ){
    console.log('offset is <= 100');
}

if( offsetHeight > 100 && offsetHeight <= 500 ){
    console.log('offset is > 100 && <= 500');
}

if( offsetHeight > 500 && offsetHeight <= 1000 ){
    console.log('offset is > 500 && <= 1000');
}
```

* If you need to animate an element using top/left/bottom/right, use it only with elements with position absolute or fixed. Changing the position of an element will modify the layout, which will force the browser to recalculate the position of all the elements affected by the movement of that one element. If you apply your changes in a absolute/fixed positioned element, the layout of other elements won't be affected

* Avoid doing expensive tasks (like modifying classes or styles, or adding/removing elements) in the onscroll event. That's a sure way to create a really poor user experience.