# Centering the unknown

How to center a container when we don't know its dimensions.

## Code

```html
<div class="container centering-parent">
  <div id="content" class="content centering-child">
    <p>This is Content! And it's centered!</p>
    <p>You can add as many or as few lines you want,</p>
    <p>it will always be centered.</p>
  </div>
</div>
```

```css
.centering-parent{
  text-align: center;
}

.centering-parent:before {
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
  margin-right: -0.25em; /* Adjusts for spacing */
}

.centering-child {
  display: inline-block;
  vertical-align: middle;
}
```

## Explanation

The `.centering-parent:before` acts like a table and `.centering-child` acts as a table cell, both allowing vertical centering.

`.centering-parent:before`, since it's `inline-block`, will take the content's element, so we give it a `height: 100%;`, and we set the baseline in the middle with `vertical-align: middle;`. Since its parent is nor a `table` nor `vertical-align: middle;`, the middle of this element will not match the parent baseline. It will be the middle of the content.

Then, we set the baseline to the middle for `.centering-child` too. Since its parent is `vertical-align: middle;` also, both baseline will be in the same place, the middle of the outter container.

You can read a full in depth explanation [here](http://gtwebdev.com/workshop/vcenter/vcenter-inline-css.php)

## Support

> \>=IE8 and real browsers

## Info

__Demo__: http://codepen.io/asainz/pen/Kpwbzv  
__Gist__: https://gist.github.com/asainz/28b4fbad2eb399bc245d

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
