# Grouping

You can have multiple selectors with the same property. Something like:

```css
.selector1 {
	background: red;
}

.selector2 {
	background: red;
}

.selector2 {
	background: red;
}
```

You are saying that .selector1, .selector2 and .selector3 have all the style `background: red`. This works and is acceptable.
But, in the future, if you want to change the background color you have to change it three times in the document.
Instead you can simple separate selectors with commas in one line or multiple lines and apply the same properties to them.

```css
.selector1, .selector2, .selector3 {
	background: red;
}
```

or

```css
.selector1,
.selector2,
.selector3 {
	background: red;
}
```

## Credits

Leonardo Lewandowski - l.lewandowski@globant.com
