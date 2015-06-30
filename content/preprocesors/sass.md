# Sass 

## Table of contents
* [Description](#description)
* [Variables](#variables)
* [Nesting](#nesting)
* [Extends](#extends)
* [Mixins](#mixins)
* [Functions](#functions)
* [Placeholders](#placeholders)
* [Sass bad practices](#sass-bad-practices)
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

### Sass bad practices

Remember Sass doesn't create bad code. Bad coders do. Let's review some bad pratices in sass:

#### Over nesting

Limit nesting as much as possible. Assess every single level of nesting that you use. This prevents increasing specificity and impacting performance. Before nesting, ask yourself "will this work without nesting?" Just because you can nest does not mean you should, or that it makes the code maintainable (Hint: it doesn't).

At most, go no more than 4 levels deep.

#### Think css/sass as html

It is a bad habit to nest every or most times an element is appears nested in the markup. CSS/SASS is not HTML, so we can't treat it in the same way. We have to be mindful of the selectors that we are compiling.

#### Over extending

Ask yourself if your compiled CSS is meant to be human readable or machine readable. If you work in Sass, but know the resulting CSS will be hand edited, I would avoid extending selectors. When using @extend two times on a single selector, there will be code related to it at three places in the CSS (assuming you aren't nesting extends).

Note: Generally, avoid using the @extend extension If you cannot, only extend placeholder classes.

#### Don't fool around with variables name

Variable names should follow this pattern: ${modifer(s)}-{name}.

The name of a variable should describe the application of the variable value. For example, instead of saying $color (which is too generic to be useful), you would write $link-color which gives the name meaning and purpose.

Similarly, the variable name can refer to specific properties such as $border-radius or $border.

Modifiers should be added before the name. So our above examples with modifiers prepended to them will look like $dark-link-color, $large-border-radius and $dotted-border.

Do note that variables without modifiers are implicitly the base version of that variable. As such, variables like $base-link-color, $base-border-radius and $base-border-radius are unnecessary.

What not to do:
```sass
$link: #ffa600;
$listStyle: none;
$radius: 5px;
```
What to do:
```sass
$link-primary: $orange;
$link-secondary: $blue;
$link-tertiary: $grey;
 
$radius-button: 5px;
$radius-tab: 5px;
```

#### Reduce Mixin Usage

A mixin is a great way to include sections of code multiple times within a site. However, including a mixin is the same as copying and pasting the styles throughout the CSS file. It creates a mass of duplicate code and can bloat your CSS file.

A mixin therefore should only be used if an argument is present, to quickly create modified styles.

#### Don't use function without thinking

Use Functions for Calculations

Functions are used to perform calculations. A Sass function does not output any CSS. Instead, it returns a value that can be used in the CSS. This is useful for calculations that will be made throughout the site.


## Info

__Demo__: http://codepen.io/mvargas21/pen/OVzwEm  
__Gist__: https://gist.github.com/souichi6666/ee9a0656a4294374f04e
## Credits

Mauricio Garcia Vargas - mauricio.garcia@globant.com