# Sticky footer with flexbox

## The problem

We need a layout that allows us to have a footer sticked to the bottom of the viewport when the content is not long enough to have a vertical scroll. When the scroll is long enough, we need the footer to move along with the content and stayed just after the content's limit.

## Solution with the footer inside the main section of the app

```html
<body class="app">
    <header class="app__navbar"></header>
    <main class="app__body">
        <div class="app__main"></div>
        <footer></footer>
    </main>
</body>
```

```css
/* setting the app's min-height to the height of the viewport */
.app { min-height: 100vh; }

/* telling the app's body and main section not to shrink and use all the empty space in the container */
.app__body, .app__main{ flex: 1; }

/* setting the whole app and its body to layout the element with flexbox in vertical direction */
.app, .app__body {
  display: flex;
  flex-direction: column;
}
```

__Demo__: http://codepen.io/asainz/pen/aOEaKm  
__Gist__: https://gist.github.com/asainz/de755cac7f98f230d810

## Solution with the footer outside the main section of the app

```html
<body class="app">
    <header class="app__navbar"></header>
    <main class="app__body">
        <div class="app__main"></div>
    </main>
    <footer></footer>
</body>
```

```css
/* setting the app's min-height to the height of the viewport */
.app { min-height: 100vh; }

/* telling the app's body and main section not to shrink and use all the empty space in the container */
.app__body, .app__main{ flex: 1; }

/* setting the whole app and its body to layout the element with flexbox in vertical direction */
.app, .app__body {
  display: flex;
  flex-direction: column;
}
```

__Demo__: http://codepen.io/asainz/pen/gpoBxJ  
__Gist__: https://gist.github.com/asainz/fc830a3644f20c2cfb8a