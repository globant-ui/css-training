# Selectors By Attribute

## Description

CSS has the ability to target HTML elements based on any one of their attributes. An attribute selector will match elements on the basis of either the presence of an attribute, or the exact or partial match of an attribute value. Attribute selectors were introduced in CSS2, and CSS3 added a few more.

Attribute selectors are delimited by square brackets; the simplest form of an attribute selector consists of an attribute name surrounded by square brackets for example:
```
tag[attribute] {
	declarations
}

[class(type of selector)name] {
	declarations
}
```

## All Selectors By Attribute 

| Name | example         | description |
| ------------- | ----------- | ----------- |
| [attribute=value]	|a[target="_blank"]	|selector is used to select elements with a specified attribute and value|
|[attribute~=value]	|[title~="flower"]	|selector is used to select elements with an attribute value containing a specified word. These examples will match elements with title="flower", title="summer flower", and title="flower new", but not title="my-flower" or title="flowers".
|[attribute&#124;=value] |[class&#124;="top"]	| selector is used to select elements with the specified attribute starting with the specified value. Match classes like class="top".
|[attribute^=value]	|[class^="top"]	|selector is used to select elements whose attribute value begins with a specified value.
|[attribute$=value]	|[class$="test"]	|selector is used to select elements whose attribute value ends with a specified value.
|[attribute*=value]	|[class*="te"]	|selector is used to select elements whose attribute value contains a specified value.

## Styling inputs

The attribute selectors can be useful for styling forms without class or ID:
```
input[type="text"] {
  width: 150px;
  display: block;
  margin-bottom: 10px;
  background-color: yellow;
}

input[type="button"] {
  width: 120px;
  margin-left: 35px;
  display: block;
}
```

## Info

__Demo__: http://codepen.io/mvargas21/pen/YXxaWV  
__Gist__: https://gist.github.com/souichi6666/c3c38277d9b3cd0dc0e8

## Credits

Mauricio Garcia Vargas - mauricio.garcia@globant.com