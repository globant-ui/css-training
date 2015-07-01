# Specificity

## Info

__Demo__: http://codepen.io/ddessaunet/pen/zGpJOg

## Description

Here is the live example from the doc sheet.

## Code

```html
<html>
  <body id="home">
    <div id="warning">
      <p class="message">CSS-Training</p>
    </div>
  </body>
</html>
```

```css
p.message {
  color: green;
}
#home #warning p.message {
  color: yellow;
}
#warning p.message {
  color: white;
}
body#home div#warning p.message {
  color: blue;
}
p {
  color: teal;
}
* body#home>div#warning p.message {
  color: red;
}
#warning p {
  color: black;
}
```

## Credits

Darío Dessaunet <dario.dessaunet@globant.com>
