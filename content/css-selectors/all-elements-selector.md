# All selector

## Description

The all selector (`*`) applies a rule to all the descendants of the preceding rule, if any is given, otherwise, it applies to all the html descendants.

## Code

```html
<html>
    <head>
        <link rel="stylesheet" href="style.css" />
    </head>
    <body>
        <ul>
            <li>Option 1</li>
            <li>
                <span>Option 2.1</span>
                <span>Option 2.2</span>
            </li>
            <li>Option 3</li>
      </ul>
    </body>
</html>
```

```css
* {
  border: 1px solid red;
}

ul * {
  border: 1px solid blue;
}
```

## Explanation

`*` is the all selector. This rule will apply the `1px solid red` border to every element in the page. The second rule will apply a `1p solid blue` border to all the descendants of the `ul`.

## Info

__Demo__: http://codepen.io/DarkThrone/pen/emQEOj  
__Gist__: https://gist.github.com/DarkThrone/9eaf390ed4830ef8d698

## Credits

Gerónimo Garcia Sgritaa <geronimo.garcia@globant.com>  
