# OOCSS

**OOCCS** aims to encourage code reuse and faster and more efficient development. This will lead, ultimately, to easier to maintain code.

There are two principles that **OOCSS** is based on:

1. [Separation on structure from skin](#separation-on-structure-from-skin)
2. [Separation on containers from contents](#separation-on-containers-from-contents)

## Separation on structure from skin

The key here is to have styles that belong to the specific branding or visual features apart from the structure.

For instance, colors, gradients or visible borders apart from floats and margins.


**bad**

```css
#button {
	width: 200px;
	height: 50px;
	padding: 10px;
	border: solid 1px #ccc;
	background: linear-gradient(#ccc, #222);
	box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

#box {
	width: 400px;
	overflow: hidden;
	border: solid 1px #ccc;
	background: linear-gradient(#ccc, #222);
	box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

#widget {
	width: 500px;
	min-height: 200px;
	overflow: auto;
	border: solid 1px #ccc;
	background: linear-gradient(#ccc, #222);
	box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
```

**good**

```css
.button {
	width: 200px;
	height: 50px;
}

.box {
	width: 400px;
	overflow: hidden;
}

.widget {
	width: 500px;
	min-height: 200px;
	overflow: auto;
}

.skin {
	border: solid 1px #ccc;
	background: linear-gradient(#ccc, #222);
	box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
```

In the first example, `#button`, `#box` and `#widget` share the same border, shadow and background. Those should be in its own class. That way, every block can concentrate in its structure (width, min-height, et cetera) and the `.skin` class can be applied to any block that needs to share the same visual effect.

## Separation on containers from contents

This implies that the content should not depend upon its container. For instance:

```
<header><div class="logo"></header>
<footer><div class="logo"></footer>
```

In that snippet, the styles that define `.logo` should not depend on its container. It doesn't matter that the logo is in the footer or the header. It's a logo, and it should always be the same. If it needs some specific differences for the header or footer, we can apply them based on the container, but only those differences.

**bad**

```css
header .logo{
    width: 100px;
    height: 100px;
    background-image: url('path/to/image.png');
    color: blue;
    margin: 5px;
}

footer .logo{
    width: 100px;
    height: 100px;
    background-image: url('path/to/image.png');
    color: blue;
    margin: 10px;
}
```
*good*

```css
.logo{
    width: 100px;
    height: 100px;
    background-image: url('path/to/image.png');
    color: blue;
}

header .logo{
    margin: 5px;
}

footer .logo{
    margin: 10px;
}
```

## Example

__Demo__: http://codepen.io/asainz/pen/RPGYMx  
__Gist__: https://gist.github.com/edcb760b3cb98f06d697  

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
