# Sass 

## Table of contents
* [Description](#description)
* [Variables](#variables)
* [Nesting](#nesting)
* [Extends](#extends)
* [Mixins](#mixins)
* [Functions](#functions)
* [Placeholders](#placeholders)
* [Info](#info)
* [Credits](#credits)

## Description

Sass is the most mature, stable, and powerful professional grade CSS extension language in the world. It's no mystery why we chose to make Sass one of our first ever series topics.

Note: Before you can use Sass, you need to set it up on your project. Go [here](http://sass-lang.com/install) if you want to learn how to get everything setup.

## Variables


Think of variables as a way to store information that you want to reuse throughout your stylesheet. You can store things like colors, font stacks, or any CSS value you think you'll want to reuse. Sass uses the $ symbol to make something a variable.

Example:

```sass

$font-stack:    Helvetica, sans-serif; /* font-stack variable defined*/
$primary-color: #333; /* primary-color variables defined */

body {
  font: 100% $font-stack; /* here the variables are applied */
  color: $primary-color;
}

```

Note: When the Sass is processed, it takes the variables we define for the $font-stack and $primary-color and outputs normal CSS with our variable values placed in the CSS.

Our example will look like this in the generated css:

```css

body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}

```
## Nesting

Sass will let you nest your CSS selectors in a way that follows the same visual hierarchy of your HTML. Be aware that overly nested rules will result in over-qualified CSS that could prove hard to maintain and is generally considered bad practice.

### Best practices 

Avoid to nesting more than three levels. Usually the 3rd level is recomenred for pseudo elements and states (:before, :hover, etc).

Is recomended to use classnames so you will avoid to nest that much.

Nesting example:

```sass

.content {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }
}

```

Generated css

```css

nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}

```

## Extends

This is one of the most useful features of Sass. Using @extend lets you share a set of CSS properties from one selector to another. It helps keep your Sass very DRY. 

### Best pratices

To sum up, here are what I would call best practices when using the @extend directive in Sass:

- Make sure the extended selector is present only once in the stylesheet.
- Avoid extending from nested selectors.
- Avoid chaining @extend directives.
- Don’t try extending from within a media query; it doesn’t work.

Extend example:

```sass

.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}

```

Generated css

```css

.message, .success, .error {
  border: 1px solid #cccccc;
  padding: 10px;
  color: #333;
}

.success {
  border-color: green;
}

.error {
  border-color: red;
}

```

## Mixins

A mixin lets you make groups of CSS declarations that you want to reuse throughout your site. You can even pass in values to make your mixin more flexible. A good use of a mixin is for vendor prefixes. 

Mixin example:

```sass
/* Mixin example without parameter in the directive definition*/
@mixin center() {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
 
.container {
  @include center();
  /* Other styles here... */
}

/* Mixin example with parameter in the directive definition*/

@mixin size($width, $height: $width) { /* in this case we are setting height using by default width, so if they are the same there is not need to put both.*/
  width: $width;
  height: $height;
}

.icon {
  @include size(32px);
}
 
.cover {
  @include size(100%, 10em);
}
 
```

Generated css:

```css
.container {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.icon {
  width: 32px;
  height: 32px;
}
 
.cover {
  width: 100%;
  height: 10em;
}

```

## Functions

It is possible to define your own functions in sass and use them in any value or script context.

A function is very similar to a mixin, and they both accept the same types of arguments, however the output from a function is a single value. This can be any Sass data type, including: numbers, strings, colors, booleans, or lists. While a mixin makes our life easier by lessening typing repetitive code, a function allows you to strip repeatable logic from your code.

Function example:

```sass
$grid-width: 40px;
$gutter-width: 10px;

@function grid-width($n) {
  @return $n * $grid-width + ($n - 1) * $gutter-width;
}

#sidebar { width: grid-width(5); }

```
Generated css:

```css
#sidebar {
  width: 240px; 
}
```

## Placeholders

Placeholders are an killer-feature added in sass 3.2. Placeholder selectors look like class and id selectors, except the # or . is replaced by %. They can be used anywhere a class or id could, and on their own they prevent rulesets from being rendered to CSS.

For example:

```sass
%button{
  display: block;
  padding: 10px;
  background: green;
}
a{ color: blue; }
```

and the css generated will be :

```css
a{ color: blue; }
```

### Placeholders working with extends

What if we created a class with the only purpose to be extended? The resulting CSS will be slightly larger than it really needs to be because we'll have a style that will never be used. We can get around this with placeholder selectors.

Example:
```sass
%icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  @extend %icon;
  /* error specific styles... */
}

.info-icon {
  @extend %icon;
  /* info specific styles... */
}
```

And the generated css will be:
```css
.error-icon, .info-icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  /* error specific styles... */
}

.info-icon {
  /* info specific styles... */
}
```
Notice how .icon is no longer present in the compiled CSS.

## Info

__Demo__: http://codepen.io/mvargas21/pen/OVzwEm  
__Gist__: https://gist.github.com/souichi6666/ee9a0656a4294374f04e
## Credits

Mauricio Garcia Vargas - mauricio.garcia@globant.com