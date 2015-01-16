# Direct ancestor selectors

This selector matches direct children of an element

## Info

__Demo__: http://codepen.io/asainz/pen/ZYexJg  
__Gist__: https://gist.github.com/asainz/0d3eefd2c1689d7c80a1

## Code

```html
<div class="container">
  <p>This is the line #1</p>
  <p>This is the line #2</p>
  <p><span>This is the line #3</span></p>
  <p>This is the line #4</p>
  <p>This is the line #5</p>
  <span>This span will not be matched by `p > span`</span>
</div>
```

```css
/* This selector will match the span elements that are a direct children of a p element */
p > span {
  background: green;
  color: white;
}
```

## Credits

Andres Sainz de Aja - andres.sainz@globant.com