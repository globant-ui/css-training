# How to make the web more accesible?

One way of making it accessible is following ARIA standard, which stands for Accessible Rich Internet Applications. Another way to improve accessiblity is by using HTML5 tags instead of regular divs. This practice is call Semantic html.

## Semantic HTML

Semantic HTML refer to how people interpret the HTML. When machine scans the code, it doesn't matter if you create a header with a <div> or a <header>. But when a human does, it does. Great deal. It's telling people what that block is supposed to mean. When a screen reader scans the HTML, it has to tell someone what the meaning of the object is, and at that moment, having the right HTML tag will make a big difference, since the reader doesn't have to infer the meaning. It's right there.

HTML5 implemented several tags with the only reason to improve semantics, and it's always recommended to use them. Some of them are:
* `<nav>`
* `<header>`
* `<footer>`
* `<article>`
* `<figure>`
* `<figcaption>`

## What is ARIA?

ARIA is a set of special accessibility attributes which can be added to HTML. Those attributes can specify what type of object is or what it does, helping the screen readers. Take into account that ARIA is implemented in most popular browsers and screen readers, but in older browser you may have close to none support.

## How do i use it

In this first example, we have an HTML snippet without ARIA attributes. Theres no indication of what each <li> means not any button.

```HTML
<!-- This is a tabs widget. How would you know, looking only at the markup? -->
<ol>
  <li id="ch1Tab">
    <a href="#ch1Panel">Chapter 1</a>
  </li>
  <li id="ch2Tab">
    <a href="#ch2Panel">Chapter 2</a>
  </li>
  <li id="quizTab">
    <a href="#quizPanel">Quiz</a>
  </li>
</ol>

<div>
  <div id="ch1Panel">Chapter 1 content goes here</div>
  <div id="ch2Panel">Chapter 2 content goes here</div>
  <div id="quizPanel">Quiz content goes here</div>
</div>
```

This is the same snippet but with ARIA attributes (note the role="" attributes). ARIA attributes are designed to be interpreted automatically by the browser and translated to the operating system's native accessibility APIs. When ARIA is present, assistive technologies are able to recognize and interact with custom JavaScript controls in the same way that they do with desktop equivalents. This has the potential for providing a much more consistent user experience than was possible in the previous generation of web applications, since assistive technology users can apply all of their knowledge of how desktop applications work when they are using web-based applications.

```HTML
<!-- Now *these* are Tabs! -->
<!-- We've added role attributes to describe the tab list and each tab. -->
<ol role="tablist">
  <li id="ch1Tab" role="tab">
    <a href="#ch1Panel">Chapter 1</a>
  </li>
  <li id="ch2Tab" role="tab">
    <a href="#ch2Panel">Chapter 2</a>
  </li>
  <li id="quizTab" role="tab">
    <a href="#quizPanel">Quiz</a>
  </li>
</ol>

<div>
  <!-- Notice the role and aria-labelledby attributes we've added to describe these panels. -->
  <div id="ch1Panel" role="tabpanel" aria-labelledby="ch1Tab">Chapter 1 content goes here</div>
  <div id="ch2Panel" role="tabpanel" aria-labelledby="ch2Tab">Chapter 2 content goes here</div>
  <div id="quizPanel" role="tabpanel" aria-labelledby="quizTab">Quiz content goes here</div>
</div>
```

## More Info

If you want to go deeper with ARIA (and you should!) check this awesome post on MDN [https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)
