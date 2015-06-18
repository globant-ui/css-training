# Basic Layout

There are several techniques to lay out content. Even though there are now advanced techniques to handle almost every scenario, there are some more basic ones, that will be suited for a good variety of scenario, without the hassle of a complicated tool, like `flexbox`.

Some of the basic ones are:

1. [Float Layout](#float-layout)
2. [Inline Layout](#inline-layout)
3. [Positioned Layout](#positioned-layout)

## Float layout

Layouting with float is maybe the most commonly used method. It's pretty easy to understand but it has some twists, as the floated elements needs to be cleared to maintaing the page flow. Thankfully we have a technique to deal with the problem called *clearfix*.
    
	.clearfix:after {
	  content: "";
	  display: table;
	  clear: both;
	}   

It may seem a little abstract, but what this does is it forces a parent element to clear for it's childrens. Take a look at the snippet to see how it's used and check this link for more information: [https://css-tricks.com/snippets/css/clear-fix/](https://css-tricks.com/snippets/css/clear-fix/)

### Example

__Demo__: http://codepen.io/Vratyas/pen/zGdWYO  
__Gist__: https://gist.github.com/Vratyas/bc14a63bbf2315ff2fa3

## Inline layout

Layouting with inline blocks is more rare but it's an option. The problem with it it's that the blocks themself tend to add a subtle margin wich can mess with the flow. There are many techniques to deal with this problem.

	<div class="grid">
	  <div class="square"></div><!--
	  --><div class="square"></div><!--
	  --><div class="square"></div><!--
	  --><div class="square"></div>
	</div>

We opted for the 'comment' technique for our snippets but check this article and choose the on that fits your project best: [https://css-tricks.com/fighting-the-space-between-inline-block-elements/](https://css-tricks.com/fighting-the-space-between-inline-block-elements/)

### Example

__Demo__: http://codepen.io/Vratyas/pen/vOJRee  
__Gist__: https://gist.github.com/Vratyas/3c13837cd8050628a20f  

## Positioned layout

### Example

__Demo__: http://codepen.io/Vratyas/pen/KpvogJ  
__Gist__: https://gist.github.com/Vratyas/ea703168f7642dd0a897  

## Credits

email: Juan Fernandez <j.fernandez@globant.com>
