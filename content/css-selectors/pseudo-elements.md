# Pseudo Elements

## Info

__Demo__: http://codepen.io/mvargas21/pen/qdjJvZ

__Gist__: https://gist.github.com/souichi6666/9c834e41a5812ceb1340

## Description

Just like pseudo-classes, pseudo-elements are added to selectors but instead of describing a special state, they allow you to style certain parts of a document.

It can be used to:

Style the first letter, or line, of an element
Insert content before, or after, the content of an element

Also, several pseudo-elements can also be combined.

Note: Sometimes you will see double colons (::) instead of just one (:). This is part of CSS3 and an attempt to distinguish between pseudo-classes and pseudo-elements. Most browsers support both values but for better practices :: should be used.

## All the pseudo elements

| Name | example         | description |
| ------------- | ----------- | ----------- |
|::after  |  p::after   | Insert content after every <p> element. This pseudo-element is used in conjunction with the content property, and additional properties can be specified to style it. Note that the generated content is only rendered—it doesn’t become part of the document tree although the generated content will of course inherit properties from it’s parent. |
|::before  | p::before   |Insert content before every <p> element,This pseudo-element represents generated content rendered before another element, and is used in conjunction with the content property|
|: disabled	|input:disabled	|Selects every disabled <input> element
|::first-letter| p::first-letter |Selects the first letter of every <p> element. This pseudo-element represents the first character of the first formatted line of text in a block-level element, an inline block, a table caption, a table cell, or a list item.|
|::first-line  | p::first-line   |Selects the first line of every <p> element. This pseudo-element represents the first formatted line of text in a block-level element, an inline block, a table caption, or a table cell.|
|::selection  |  p::selection  |  Could be associated to an element or to the document. This pseudo-element represents a part of the document that’s been highlighted by the user


## Code example

    //Places '*' before every element with titles class. 
    .titles::before {
        content: '*';
    }
    //Places '--' before after element with titles class. 
    .titles::after {
        content: '--';
    }

## Credits

Mauricio Garcia Vargas - mauricio.garcia@globant.com