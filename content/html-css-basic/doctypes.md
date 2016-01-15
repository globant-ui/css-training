# Doctypes

The doctype identifies the type of document that follows, and appears just above the <html> tag, at the very start of each HTML document. The doctype tells the browser the type of HTML to expect, and therefore what validators it should validate your document against.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My awesome page!<</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
        <p>Thanks for coming</p>
    </body>
</html>
```
## Why is important to specify the correct doctype?

The doctype also serves to make the browser render the page in "standards mode". In standards mode, browsers try to render the page according to the CSS specifications, in effect trusting that the person who created the document knew what they were doing.

On the other hand, if a browser finds an outdated, incomplete, or missing doctype at the start of the page, it will render the page using "quirks mode", which is more backward-compatible with older practices and browsers. Quirks mode assumes that the document was not created with web standards in mind. In practical terms it means that the web page will still render, but the browser will work a bit harder to do so, and you may get some unexpected display results. The differences are mostly about how the CSS is rendered, and only partly about how the actual HTML is treated.

## What should i use?

As of HTML5, the standard and recommended is

```html
<!DOCTYPE html>
```

By using that one, you will be sure browsers use standards mode and will work best when you follow web standards.
