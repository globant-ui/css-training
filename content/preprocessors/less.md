# LESS

## Table of contents
* [Description](#description)
* [Variables](#variables)
* [Nesting](#nesting)
* [Extends](#extends)
* [Mixins](#mixins)
* [Merge](#merge)
* [Less bad practices](#less-bad-practices)
* [Credits](#credits)

## Description

Less is a preprocessor, just like sass or stylus. It's written in node and it allows you to use mixinx, functions, variables and nesting. Those are pretty similar but they have different syntax.

## Variables

You can store values in variales, just like in any programming language. You can make calculations with them

```css
@main-color: #1010ff;
@secondary-color: @main-color + #bbbbbb;

.main{
  color: @main-color;
  background: @secondary-color;
}
```

it will output

```css
.main {
  color: #1010ff;
  background: #cbcbff;
}
```

## Nesting

You can nest your selectors to simplify writing complex selectors, emulating the html structure

```css
@main-color: tomato;
@secondary-color: orange;

.main{
  background: @main-color;
  
  .items-list{
    padding: 0;
    margin: 0;
    
    .item-list{
      padding: 1em;
      background: @secondary-color;
      
      &:hover{
        box-shadow: 0 0 10px 0 @main-color;
      }
    }
  }
}
```

it will output

```css
.main {
  background: #ff6347;
}
.main .items-list {
  padding: 0;
  margin: 0;
}
.main .items-list .item-list {
  padding: 1em;
  background: #ffa500;
}
.main .items-list .item-list:hover {
  box-shadow: 0 0 10px 0 #ff6347;
}
```

## Extends

LESS docs say "Extend is a Less pseudo-class which merges the selector it is put on with ones that match what it references.". Basically, it replaces a classname with another one.

If you have something like this

```css
.parent-class{
    color: red;
}

.child-class{
    &:extend(.parent-class);
}
```

It will take the `child-class` name and put it wherever `.parent-class` appear in the output code. You can see a more complex example below. Take into account that `extend` doesn't replace the nesting selectors. If you need that, you have to do it manually, as shown below `&:extend(.default-button a);`.

```css
.default-button{
  background: gray;
  border-radius: 5px;
  display: block;
  width: 100%;
  color: black;
  
  a{
    text-decoration: none;
  }
}

.main-button{
  &:extend(.default-button);
  
  a{
      &:extend(.default-button a);
  }
  
  background: red;
}
```

it will output

```css
.default-button,
.main-button {
  background: gray;
  border-radius: 5px;
  display: block;
  width: 100%;
  color: black;
}
.default-button a,
.main-button a {
  text-decoration: none;
}
.main-button {
  background: red;
}
```

For more advanced usage of extends, take a look at less documentation [http://lesscss.org/features/#extend-feature](http://lesscss.org/features/#extend-feature)

## Mixins

Mixins let you combine properties in existing classes

```css
```

it will output

```css
.highlighted-border{
    border: 1px solid red;
}

.button{
    .highlighted{
        .highlighted-border();
    }
}
```

it will output

```css
.highlighted-border {
  border: 1px solid red;
}
.button .highlighted {
  border: 1px solid red;
}
```

This is the simplest form. For more complex configurations, take a look at the less documentation [http://lesscss.org/features/#mixins-feature](http://lesscss.org/features/#mixins-feature)

## Merge

Merge lets you agreggate properties in a comma separated list

```css
.highlighted-shadow{
    box-shadow+: 0 0 10px 0 rgba(0,0,0,.5);
}

.button{
    .highlighted{
        .highlighted-shadow();
            box-shadow+: 0 0 20px 0 rgba(0,0,0,.9);
    }
}
```

it will output

```css
.highlighted-shadow {
  box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.5);
}
.button .highlighted {
  box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.5), 0 0 20px 0 rgba(0, 0, 0, 0.9);
}
```

## Less bad practices



## Credits

Andrés Sainz de Aja - andres.sainz@globant.com