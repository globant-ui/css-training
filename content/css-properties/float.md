# Float

A floated element will be takend from the normal flow of the document and places either on the left or the right side of its container.

You can think of floated elements as having their own flow in the container. That means that a floated element will be taken all the way right or left until they collide with the edge of the container or another floated element. All text or inline elements will wrap arround a floated element.

As the float value is expected to be applied to block elements, you'll see that it affects the computed value for said property. Meaning that elements declared as inline-block or table-row for example, will be converted to block elements.

Floating elements tend to have some drawbacks if you are not familiar with them. You'll see for example that a floated element may turn its container into a 0x0px box, this is due to the element beign outside of the normal flow of the container. Thankfully we have the clearfix technique to deal with this kind of problems.

## Clear

The clear property determines weather an element can be next to floating elements or if it should be moved down below them, efectivly breaking the floated flow. You can either specify if you want to clear an elements wich has floated elements on it's right or left side. Or in the case in which the element is preceded by both right and left floated elements, you can use the both value.

## Clearfix technique

	.clearfix:after {
	  content: "";
	  display: table;
	  clear: both;
	}

What this little weird piece of code is that it forces an element to clear for it's children. That means that an element containing floated elements will maintaing it's normal behavior in terms of size and positioning.

#### Info

__Demo__: http://codepen.io/Vratyas/pen/VLrdPq 
__Gist__: https://gist.github.com/Vratyas/edc6f17cb8dfd44e2f86

#### Credits

Juan Fernandez - <j.fernandez@globant.com>
