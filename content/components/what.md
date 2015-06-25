# What are the components?

Components are reusable, atomic parts of the app. Together, the will form a app view or page. 

## What do they look like in css?

Well, a component is nothing more (and nothing less) than a class. You can choose to follow yhe standards you want ([take a look here](content/architecture-medium/README.md)), but a `.form` component will look very similar to the following snippet.

```html
<div class="form">
    <div class="form--control">
        <label for="">email</label>
        <input type="text" class="form--field">
    </div>

    <div class="form--control">
        <label for="">password</label>
        <input type="password" class="form--field">
    </div>

    <div class="form--control">
        <input type="submit" class="form--field" value="Send">
    </div>
</div>
```


```css
.form{
    border: 1px solid black;
}

.form--control{
    padding: 1em;
    margin: 1em;
    background: #f2f2f2;
}

.form--control label{
    display: block;
    font-weight: bold;
}

.form--control .form--field{
    display: inline-block;
    width: 100%;
    padding: .5em;
}
```

There you go. It looks really simple, and it is! You have a very very simple `.form` component. Of course a real one will need more details and inner elements, but the main idea is there. In that bit of css you have encapsulated the css rules needed to display a simple form. If you have to implement that form in several pages, the only thing you need to think about is that you use the correct classes and elements the component needs to work. You do that and you rest asure the component will look like the same in the whole app. If someday someone asks for a change in the form, change one definition and the whole app si updated the same.