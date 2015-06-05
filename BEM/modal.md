# Vertical centering techniques

## Info

__Demo__: http://codepen.io/asainz/pen/waworL  
__Gist__: https://gist.github.com/asainz/105c8a2014a28a8dbcd8

## Description

In the example, we have defined:

#### block

`modal` defines the whole component. It is created for each element.

#### element

`background` adds a dimmed screen that cover what's beneath the modal.  
`content` is where the modal content is. Its porpuse is to style and position it in the viewport.  
`title` styles the title. It is an element because this particular styling for a title is directly connected to a modal.  
`copy` styles the content copy. It is an element because this particular styling for a title is directly connected to a modal.  
`action-buttons` is a container for the modal buttons. Its porpuse is to style and position it in the modal__content element.  

#### modifier

`action-buttons-stacked` modifies the behavior of the action-buttons element, by stacking the buttons.

### Why is the .logo class not an element?

`.logo` it is not an element since its styles are not specific not related to a modal. A `.logo` (in this example) has to look the same whereever it is placed.

## Credits

Andres Sainz de Aja - andres.sainz@globant.com