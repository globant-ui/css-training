# Vertical Rhythm

'Vertical Rhythm' defines a set of rules to maintain coherency between elements height, borders, paddings, margin and whitespace.

When making a web page or web application, it is common to see variations in things like font size on headers and text, illustrations and vertical white space. This kind of variations tend to generate visual discrepancies. The concept of Vertical Rhythm defines says that the vertical white space between the different kind of elements based on the font baseline.

You can choose to implement Vertical Rhythm rules however you please, but the easiest method may be by using a third party library. I personally would recommend using compass if you happen to be using sass as a preprocessor. But if you are not using a preprocessor go check out [this article](http://webdesign.tutsplus.com/articles/improving-layout-with-vertical-rhythm--webdesign-14070) to find some alternatives or [this one](http://www.smashingmagazine.com/2012/12/17/css-baseline-the-good-the-bad-and-the-ugly/) to get an idea on how to implement it on your own.
I do recommend checking out the snippet we made to see an implementation of Vertical Rhythm and it's behavior.

Compass provides already a set of mixins that calculates this for us, based on a defined set of variables called $base-font-size and $base-line-height.

    $base-font-size: $font-size-normal; (16px);
    $base-line-height: 24px;

## Info

__Demo__: http://codepen.io/Vratyas/pen/WvXBvv
__Gist__: https://gist.github.com/Vratyas/b2cfea52241e42d334d9

## Credits

email: Juan Fernandez <j.fernandez@globant.com>
