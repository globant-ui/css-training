# Reset vs Normalize

Thank god we have standards right? Wrong. Every browser implements their user agents in their own way, and so, default css styles tend to differ from one browser to another. Thankfully some people went ahead and solved the problem for you. There are many many ways of reseting default css, but we choose to present you with the two most common used methods.

## [Reset](http://meyerweb.com/eric/tools/css/reset/) by Eric Meyer

According to Meyer itself:

> The goal of a reset stylesheet is to reduce browser inconsistencies in things like default line heights, margins and font sizes of headings, and so on

### What does it do?

* The reset styles given here are intentionally very generic.
* There isn't any default color or background set for the body element, for example.
* It should be tweaked, edited, extended, and otherwise tuned to match your specific reset baseline.

### Disadvantages

* Reset declarations can really clog your inspector when you try to trace styles.
* Resets don't attempt to normalize specific cross-browser issues or set helpful styles.

## [Normalize](https://github.com/necolas/normalize.css/) by Nicolas Gallagher

Normalize in words of his own creator is:

> A small CSS file that provides better cross-browser consistency in the default styling of HTML elements. It’s a modern, HTML5-ready, alternative to the traditional CSS reset.

### What does it do?

* Preserves useful defaults, unlike many CSS resets.
* Normalizes styles for a wide range of elements.
* Corrects bugs and common browser inconsistencies.
* Improves usability with subtle improvements.
* Explains what code does using detailed comments.


### Disadvantages

* Declarations that aren't helpful. What's the point in specifying arbitrary sizes for headings when you are going to overwrite them all anyway?
* Support for browsers you might not need to support. Do you really need the IE8 hacks?
* It's over 8 KB. Hopefully you strip the comments, minify and include it in the main stylesheet to avoid an extra network request, but I know a lot of you don't.

#### Credits

Juan Fernandez - <j.fernandez@globant.com>
