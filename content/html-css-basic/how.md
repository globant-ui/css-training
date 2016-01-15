# How to create an HTML page

Ok, let's start for the beginning. HTMl. What?

## What is HTML?

HTML is a language used to describe the contents of web documents. It uses a syntax containing markers (called elements) that are wrapped around content in the document to indicate how user agents (e.g., web browsers) should interpret that portion of the document.

```HTML
<h1>This is my first HTML!</h1>
<img src="my-image.png />"
```

In the previous snippet, ``<h1>`` is an element or tag (FYI, h1 stands for Heading 1). `</h1>` is a closing tag. All tags must have a closure. `<img />` is an special type of tag; it's a self-closing one.

[You have a list of **all** html tags in MDN](https://developer.mozilla.org/en/docs/Web/HTML/Element)

## Creating the most basic HTML page

In its most basic form, and HTML page has a couple of mandatory elements, such as `<html>`, `<body>` and `<head>`. Some are not mandatory, but it's very important they're there, like `<title>`.

```HTML
<html>
    <head>
        <!-- Inside <head> elements is where you configure or set up the page, indicating what resources it will use or telling the browser hot to render specific parts of it. -->
        <!-- By the way, you can add HTML comments by wrapping text between this funky symbols! -->
        <title>My awesome page!<</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
        <p>Thanks for coming</p>
    </body>
</html>
```
