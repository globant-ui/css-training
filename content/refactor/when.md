# When do i need a refactor?

At one time or another you'll be tasked to maintain or add further development to a existing css basecode. Sometimes the basecode will be in a good shape and sometimes it will be in a very bad shape, and it will require major changes to make it more scalable, reusable and maintainable.

## What things should raise a red flag?

There are some scenarios that will likely be cumbersome (maybe they are already) to maintain and change. Here's a list of things we found that should take your attention. If you found one or more of this in the codebase (by experience, if you find one, you will find more), you'll definetly have to start thinking in a refactoring.

1. [Lots and lots of `!important`](#lots-and-lots-of-important)
2. [Heavily overqualified selectors](#heavily-overqualified-selectors)
3. [Different classes addressing the same problem](#different-classes-addressing-the-same-problem)
4. [Lots and lots of styles applied by id](#lots-and-lots-of-styles-applied-by-id)
5. [Lots and lots of inline css](#lots-and-lots-of-inline-css)
6. [The same class defined in different places](#the-same-class-defined-in-different-places)

We'll go one by one.

### Lots and lots of `!important`

We all have used `!important` some time, even though we know most of the times its use it's not justified. As we've seen in previos chapters, `!important` messes up the natural cascading and makes debugging more difficult.

There are some excepcions to the no-important rule. Sometimes, you are implementing a state class that has to override whaever value the element has. For instance, a `.is-active` class that should change the backgroung color to orange, no matter who or when set it differently. In that case, since we could't know the specificity of the selector that applied it, `!important` comes in handy, in a non-harmful way.

When you see a codebase that is flooded with `!important`s, be aware. That codebase will possibly be an specificity nightmare. A codebase flooded with `!important`s means that you cannot rely on cascade nor specificity, and in order to implement changes in the visuals, you will probably need to add even more `!important`s, mangifying the problem.

### Heavily overqualified selectors

This is like the opposite situation to the `!important` problem. Overqualifying appears when the natural cascade is broken and we need start adding specificity to the selectors in order to override some styles that comes from god knows where.

Overqualified selectors look like this

```css
#nav > .nav-content ul li a {
    color: red;
}
```

The problem with this situation is that the selectors are very tightly coupled to the HTML structure, and a minor change in it, like adding a `div` between `#nav` and `.nav-content` will break the selector. Plus, if we need to override the styles of that `a` (for instance, paint it differently if that `a` has a submenu), just adding a class won't do the trick, since the specificity of that selector is gigantic, and we would end up doing something like this:

```css
#nav > .nav-content ul li a.has-submenu {
    color: white;
    background: red;
}
```

or, even worse, something like this:

```css
#nav .has-submenu {
    color: white !important;
    background: red !important;
}
```

### Different classes addressing the same problem

For example, you have a list of items where each item has a main content, centered horizontally, and a button in both each sides. In another page, you have the same list, but the main content is aligned to the left. Ideally, you would have somethink like a `.list` component and a `.list--left-aligned` modifier to that module.

But, what if you have a `.list` module and a `.list-left` module, both implementing almost the same things (probably they were made by different people, so probably implemented in a different way) with only a alignment change? That means problem, because if you need to make a change in those two lists, you need to duplicate the change in both classes. When you're presented with this scenario, it almost always means that the basecode wasn't created with reusability in mind, and that you should expect worse things that this.

### Lots and lots of styles applied by id

This is an extension of the overqualifying problem. First of all, ids are not reusable, so applying styles by id means you're not going to be able to use that anywhere in the app. If that's not bad enough, ids have a greater specificity that classes, so if someone added ids in every selector, you have to remove them from the css and html or create your classes with ids or `!imporatnt`s. Whaever you do, it will not be pretty.

### Lots and lots of inline css

Again, this is another extension of the overqualifying problem. Inline css have a greater specificity even than ids! So if you are given a basedcode flooded with inline css, you will have no other option that remove them and replacing then with classes.

### The same class defined in different places

Maybe there are different css files in the project, and someone had to implement a class and used a generic name like `.title` and didn't namespace it. Then, another dev implemented the same class in another file, maybe for another part of the app. The styles collide, you don't know what's happening, and you are not sure which class is the good one and what should be removed (of course, those devs already left the project).