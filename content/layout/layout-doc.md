# Basic Layout

## [Snippets](layout-snippet.md)

## Float layout

Layouting with float is maybe the most commonly used method. It's pretty easy to understand but it has some twists, as the floated elements needs to be cleared to maintaing the page flow. Thankfully we have a technique to deal with the problem called *clearfix*.
    
	.clearfix:after {
	  content: "";
	  display: table;
	  clear: both;
	} 

It may seem a little abstract, but what this does is it forces a parent element to clear for it's childrens. Take a look at the snippet to see how it's used and check this link for more information: [https://css-tricks.com/snippets/css/clear-fix/](https://css-tricks.com/snippets/css/clear-fix/)

## Inline layout

Layouting with inline blocks is more rare but it's an option. The problem with it it's that the blocks themself tend to add a subtle margin wich can mess with the flow. There are many techniques to deal with this problem.

	<div class="grid">
	  <div class="square"></div><!--
	  --><div class="square"></div><!--
	  --><div class="square"></div><!--
	  --><div class="square"></div>
	</div>

We opted for the 'comment' technique for our snippets but check this article and choose the on that fits your project best: [https://css-tricks.com/fighting-the-space-between-inline-block-elements/](https://css-tricks.com/fighting-the-space-between-inline-block-elements/)

