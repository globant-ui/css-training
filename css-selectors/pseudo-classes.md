# Pseudo classes 

## Info

__Demo__: http://codepen.io/mvargas21/pen/MwmXYP

__Gist__: https://gist.github.com/souichi6666/b22ec72fbb5379bb8386
## Description

A CSS pseudo-class is a keyword added to selectors that specifies a special state of the element to be selected.

It can be used to:

- Style an element when a user mouses over it
- Style visited and unvisited links differently

#### All the pseudo classes

| Name | example         | description |
| ------------- | ----------- | ----------- |
|:active	|a:active	|Selects the active link|
|:checked	|input:checked	|Selects every checked <input> element
|: disabled	|input:disabled	|Selects every disabled <input> element
|:empty	|p:empty	|Selects every <p> element that has no children
|:enabled	|input:enabled	|Selects every enabled <input> element
|:first-child	|p:first-child	|Selects every <p> elements that is the first child of its parent
|:first-of-type	|p:first-of-type	|Selects every <p> element that is the first <p> element of its parent
|:focus	|input:focus	|Selects the <input> element that has focus
|:hover	|a:hover	|Selects links on mouse over
|:in-range	|input:in-range	|Selects <input> elements with a value within a specified range
|:invalid	|input:invalid	|Selects all <input> elements with an invalid value
|:lang(language)|	p:lang(it)	|Selects every <p> element with a lang attribute value starting with "it"
|:last-child	|p:last-child	|Selects every <p> elements that is the last child of its parent
|:last-of-type	|p:last-of-type	|Selects every <p> element that is the last <p> element of its parent
|:link	|a:link	|Selects all unvisited links
|:not(selector)	|:not(p)	|Selects every element that is not a <p> element
|:nth-child(n)	|p:nth-child(2)	|Selects every <p> element that is the second child of its parent
|:nth-last-child(n)	|p:nth-last-child(2)	|Selects every <p> element that is the second child of its parent, counting from the last child
|:nth-last-of-type(n)	|p:nth-last-of-type(2)	|Selects every <p> element that is the second <p> element of its parent, counting from the last child
|:nth-of-type(n)	|p:nth-of-type(2)	|Selects every <p> element that is the second <p> element of its parent
|:only-of-type	|p:only-of-type	|Selects every <p> element that is the only <p> element of its parent
|:only-child	|p:only-child	|Selects every <p> element that is the only child of its parent
|:optional	|input:optional	|Selects <input> elements with no "required" attribute
|:out-of-range	|input:out-of-range	|Selects <input> elements with a value outside a specified range
|:read-only	|input:read-only	|Selects <input> elements with a "readonly" attribute specified
|:read-write	|input:read-write	|Selects <input> elements with no "readonly" attribute
|:required	|input:required	|Selects <input> elements with a "required" attribute specified
|:root	|root	|Selects the document's root element
|:target	|#news:target	|Selects the current active #news element (clicked on a URL containing that anchor name)
|:valid	|input:valid	|Selects all <input> elements with a valid value
|:visited	|a:visited	|Selects all visited links


#### Code example

    /* set unvisited link to blue*/
    a:link {
        color: blue;
    }
    /* set visited link to red */
    a:visited {
        color: red;
    }
    /* set on mouse over yellow */
    a:hover {
        color: yellow;
    }

## Credits

Mauricio Garcia Vargas - mauricio.garcia@globant.com