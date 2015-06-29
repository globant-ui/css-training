# Centering the unknown with flexbox

This is the same scenario as depicted in [Centering the unknown](content/alignment/centering-the-unknown.md) but solved more easily with flexbox

## Code

```html
<div class="container">
  <div id="content" class="content">
    <p>This is Content! And it's centered!</p>
    <p>You can add as many or as few lines you want,</p>
    <p>it will always be centered.</p>
  </div>
</div>
```

```css
/* we are simply using the natively centering properties provided by flexbox */
.container{
  display: flex;
  flex-direction: column;
  justify-content: center;
}
```

## Info

__Demo__: http://codepen.io/asainz/pen/RPxeMd
__Gist__: https://gist.github.com/asainz/eb1342ece79b21667c01

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
