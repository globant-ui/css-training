# Global Scopes

## What is it?

Global scope means that a css rule is applied to the whole app. For example, you have this rule

```css
.title{
    font-size: 20px;
    color: tomato;
}
```

The class `.title` will be applied to every element that has the `title` class assigned to it, in every page of the app. That seems to be alright, but that's a fairly generic class name, and many parts of the app may have it in them with different implementations (e.g. different color and font-size). You will sooner or later find problems with generic class names in the global scope.

## How can you avoid it?

There two ways of achieving that, that are commonly used: `namespaces` and `prefixes`

### namespaces

A namespace is a class that wraps all the rules that belong to a page or component. By using that, we will avoid collision between different pages implementing the same generic classname.

```html
<div class="login-page">
    <h1 class="title"></h1>
    <div class="content">
        <p></p>
    </div>
</div>

<div class="dashboard-page">
    <h1 class="title"></h1>
    <div class="content">
        <p></p>
    </div>
</div>
```

```css
.login-page .title {
    font-size: 22px;
    color: red;
}

.dashboard-page .title {
    font-size: 20px;
    color: blue;
}
```

### prefixes

You can prefix a name convention to a class, in order to differentiate one another. This is not recommended to wrap classes that belong to a page or component, since it will require that every one of the classes has the prefix. Prefixes are useful in other scenarios, where you need, for example, to add a class that's intended to work as a js hook, so you can do something like `js-login-page`.

```html
<div>
    <h1 class="lp-title"></h1>
    <div class="lp-content">
        <p></p>
    </div>
</div>

<div>
    <h1 class="dp-title"></h1>
    <div class="dp-content">
        <p></p>
    </div>
</div>
```

```css
.lp-title {
    font-size: 22px;
    color: red;
}

.dp-title {
    font-size: 20px;
    color: blue;
}
```

## Are global scopes useful?

Yes! They are useful, but you have to be cautious about them. One of the most common uses is for reseting or normalizing. For example, maybe you want all of your `li` not to have bullets on the side, or you want the `a` not to have an underline. In this cases, global css are the way to go.

```css
li {
    list-style: none;
}

a {
    text-decoration: none;  
}
```

## Credits

Andres Sainz <andres.sainz@globant.com>