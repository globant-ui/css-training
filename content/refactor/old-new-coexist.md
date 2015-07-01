# How can you make the old css and new css coexist?

A very important aspect of a css refactor is to be able to have both the old and new css live together while the new one is fully implemented.

What you need accomplish is:

1. Reset any style that the old css is applying in the elements
2. If you're changing the markup too, make sure the new styles don't apply to any of the html that hasn't been changed yet.

## Namespacing the new stuff

One simple but effective solution is to namespace everythings that's new (HTML or CSS) in a class that can be used in the selectors to target the new or the old. When the refactor is complete, you have to remove that class from everywhere and you're done.

```html
<!-- old html -->
<div>
    <div class="items">
        <div class="item"></div>
        <div class="item"></div>
        <div class="item"></div>
        <div class="item"></div>
    </div>
</div>
```
<!-- old css -->

```css
div{
    padding: 1em !important;
}

.items{
    background: blue;
}

.item{
    margin: 1em;
}
```

```html
<!-- new html with the namespace -->
<div class="refactor">
    <ul class="items">
        <li class="item"></li>
        <li class="item"></li>
        <li class="item"></li>
        <li class="item"></li>
    </ul>
</div>
```

```css
<!-- new css with the namespace -->

<!-- reset the old stuff -->
.refactor div{ padding: 0; }
.refactor .items{ background: transparent; }
.refactor .item{ margin: 0; }

<!-- now, apply the new styles -->
.refactor .items{
    border: 1px solid black;
    padding: .5em;
}

.refactor .item{
    margin: 2em;
}
```

In this example we can see how we can implement the namespace solution. After the refactor is complete, we can remove the `.refactor` class from the html and css and remove all the rules we created for refactoring. In order to simplify the process, we separated the reset stuff from the actual styling.