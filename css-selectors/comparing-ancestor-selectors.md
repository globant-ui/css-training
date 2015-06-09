# Comapring ancestor selectors

## Info

__Demo__: http://codepen.io/asainz/pen/KwWYyV  
__Gist__: https://gist.github.com/asainz/69ded22a952b62c0297a  
__Screencast__: https://www.youtube.com/watch?v=gRWbt_Seas0

## Code

```html
<section class="container">
  <p>This is the line #1</p>
  <p>This is the line #2</p>
  <div><p>This is the line #3</p></div>
  <p>This is the line #4</p>
  <p>This is the line #5</p>
</section>
```

```css
/* (1) */
/* this selector will paint green all elements inside a section element, no matter how deep they are. */
section p{
  background: green;
}
 
/* (2) */
/* this selector will paint red all p elements that are a direct child of a section element */
section > p{
  background: tomato;
}
```

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
