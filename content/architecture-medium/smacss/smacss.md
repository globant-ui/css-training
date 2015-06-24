# SMACSS

**SMACSS** aims to encourage code reuse and faster and more efficient development, as any css modularization standard.  

**SMACSS** has categorization at its core to provide modularity. By categorizing CSS rules, we will find patterns, and **SMACSS** helps us to handle those patterns in a clear, reusable way.  

## Categorization

There are five types of categories:

1. [Base](#base)
2. [Layout](#layout)
3. [Module](#module)
4. [State](#state)
5. [Theme](#theme)

### Base

These are the defaults values, often applied to single element or pseudo element selectors, like a reset.

```css
html, body { height: 100%; }
h1, h2, h3, h4, h5, h6, p { margin: .5em 1em; }
a:visited { text-decoration: none; }
input[type=text] { border: 1px solid #999; }
```

### Layout

These divide the page into sections. Layouts hold one or more modules together.

### Module

These are the reusable, modular parts of our design. They are the callouts, the sidebar sections, the product lists and so on.

### State

These are ways to describe how our modules or layouts will look when in a particular state. Is it hidden or expanded? Is it active or inactive? They are about describing how a module or layout looks on screens that are smaller or bigger. They are also about describing how a module might look in different views like the home page or the inside page. Normally, state classes are allowed to use `!important`, since they have to override the state set by the module.

### Theme

These are similar to state rules in that they describe how modules or layouts might look

## Naming conventions

**SMACSS** usually uses a prefix to differentiate between layout, state and module rules.

* For layout, `l-`
* For state, `is-`

Modules don't normally use prefix. Its child are prefixed with the module's name.

```css
.modal { }
.modal-buttons { }
.modal-buttons button.is-selected { }

.l-buttons-stacked { }
.l-buttons-inline { }
```

## Example

__Demo__: http://codepen.io/asainz/pen/eNEoqy    
__Gist__: https://gist.github.com/670c872862659e54a190    

## Credits

Andres Sainz de Aja - andres.sainz@globant.com
