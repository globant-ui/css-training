# Siblings selectors

There are two differnts sibling selectors: `+` and `~`.

## Info

__Demo +__: http://codepen.io/asainz/pen/rayGLK  
__Gist +__: https://gist.github.com/asainz/f01fac82c4d2c41d5b0c

__Demo ~__: http://codepen.io/asainz/pen/NPpajj  
__Gist ~__: https://gist.github.com/asainz/d70f7d9e6f85c94416d6

## Description

The `+` selector matches the element that is immediately following the first element.  
The `~` selector matches all elements that are immediately following the first element.

It is important to note that both selectors match elements that are in the same level as the first element.

## Code

```html
<div class="container-direct-sibling">
  <p>This is the line #1</p>
  <p class="target">This is one target element</p>
  <p>This is the line #2</p>
  <p>This is the line #3</p>
  <p class="target">This is another target element</p>
  <div>
    <!-- This p will not be matched since it's inside a div, one level down -->
    <p>This is the line #4</p>
  </div>
</div>

<div class="container-all-siblings">
  <p>This is the line #1</p>
  <p class="target">This is the target element</p>
  <p>This is the line #2</p>
  <div>
    <!-- This p will not be matched since it's inside a div, one level down -->
    <p>This is the line #3</p>
  </div>
  <p>This is the line #4</p>
  <p>This is the line #5</p>
</div>
```

```css
/* this selector will match the p element that is directly following a .target element */
.container-direct-sibling .target ~ p{
  background: green;
  color: white;
}

/* this selector will match all p elements that are directly following a .target element */
.container-all-siblings .target ~ p{
  background: green;
  color: white;
}
```

## Credits

Andres Sainz de Aja - andres.sainz@globant.com