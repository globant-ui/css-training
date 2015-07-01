# Real life examples

## Comments section

Let's create a comments section for a blog. Each comment will have an avatar and the message. Plus, each comment can have responses, that will contain also an avatar an a message. We can think of it as a comment can have other comments in response. So, a components should come up: the comments.

### Let's build it!

We know that each comment has to have an avatar and a message. We can create something like this (as a reference, i'm using BEM sintax, but the chosen sintax is not relevant for this explanation):

```html
<div class="comment-box">
    <div class="comment-box__body">

        <div class="comment-box__avatar">
            <img src="http://placehold.it/60x60" alt="" />
        </div>

        <div class="comment-box__content">
            <p>Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet.</p>
        </div>

    </div>
</div>
```

And now, let's add some basic styling to place the message next to the avatar using flexbox (again, the chosen method for the layout is not relevant in this explanation):

```css
.comment-box{  
  background: #f2f2f2;
  padding: .5em;
}

.comment-box__body{
  display: flex;
  justify-content: space-between;
}

.comment-box__avatar{
  flex-shrink: 0;
}

.comment-box__content{
  margin-left: 1em;
}
```

__Demo__: http://codepen.io/asainz/pen/bdYPjL  

As you can see, it's really simple. It probably will need more styling to make it look like a real comments section message, but you get the idea. The beauty of having it as a component is that you can nest it, and you won't need to worry about laying out the responses. Try adding it a `.comment-box` below the `.comment-box__body` block.

__Demo__: http://codepen.io/asainz/pen/doZBqM  

Pretty good. It almost looks like a message with responses. What we do now is what every component need: some variations for specific cases.

Let's add this bit of css

```css
.comment-box > .comment-box{
  margin-left: 4em;
  margin-top: 1em;
  
  background: #e1e1e1;
}
```

What we're doing now is just adding some margin and different background to the `.comment-box` elements that are children of another `.comment-box` element. It's a very good to style the responses a bit different than the original comment without adding new classes.

__Demo__: http://codepen.io/asainz/pen/xGPoyb  

Suddenly, it looks much better. Of course, it needs more detailing in order to make it production-ready. But the important thing is that you get the idea of how to create a component and how useful it is, even in small examples like this one.


### Full demo:

__Demo__: http://codepen.io/asainz/pen/waPLdq  
__Gist__: https://gist.github.com/asainz/3bc78ac204e916982840