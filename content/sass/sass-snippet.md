# Sass

## Info

__Demo__: http://codepen.io/Vratyas/pen/xbqjgX?editors=110
__Gist__: https://gist.github.com/Vratyas/f20d0477dcc09e810cad

## Description

A set of basic snippets showing the most important aspects of the sass language.

## Code

```html
<div class="snippets">
  
  <h1>Sass Snippets</h1>

  <h2>Variables</h2>
  
  <p>Just like a programming language, sass allow us to define variables for things like numbers, colors, strings, etc. <br />
  In this example we are storing the text color and font size;
  </p>
  
  <div class="example-variables">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non eveniet, qui officia eius et quam voluptate, ab ipsa deserunt rerum maiores aliquam modi delectus illo. Eveniet sint, minus! Suscipit, illum.</p>
  </div>
  
  <h2>Operators</h2>
  
  <p>Sass allow us to operate over values or variables of any kind. <br />
  In this example we are showing operations over numbers and colors.
  </p>
  
  <div class="example-operators">
    <div>
      <span class="box">50px</span>
      <span class="operator">+</span>
      <span class="box">50px</span>
      <span class="operator">=</span>
      <span class="box result-box">100px</span>
    </div>
    <div>
      <span class="color primary-color"></span>
      <span class="operator">-</span>
      <span class="color secondary-color"></span>
      <span class="operator">=</span>
      <span class="color result"></span>
    </div>
  </div>
  
  <h2>Nesting</h2>
  
  <p>Sass allow us to nest our css rules the same way we nest our html elements. In this example we have a list within a list nested both in html and css to have a different text color.</p>

  <div class="example-nesting">
    <ul>
      <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quas enim perspiciatis quidem ratione dicta laudantium dolorum quisquam itaque, assumenda corporis sunt quaerat culpa veniam qui dolore saepe porro veritatis! Similique</li>
      <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad aliquid quam neque ab iste fugit numquam, ea debitis explicabo placeat quidem quae accusantium dolorem atque voluptatibus maxime distinctio eos a.</li>
      <li>
        <ul>
          <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ratione ab minus sint esse rem asperiores, qui nam, quisquam possimus perferendis, repudiandae? Non dolorem reiciendis labore eaque. Et dolores, ut qui.</li>
          <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ratione ab minus sint esse rem asperiores, qui nam, quisquam possimus perferendis, repudiandae? Non dolorem reiciendis labore eaque. Et dolores, ut qui.</li>
        </ul>
      </li>
    </ul>
  </div>
  
  <h2>Mixins</h2>
  
  <p>Mixins on sass are little pieces of css declarations that you will want to reuse across your application. You can pass variables to a mixins just like a function. In this examples the gray boxes use a mixin yo apply a border radius.</p>
  
  <div class="example-mixins">
    <div class="box">Box</div>
    <div class="box rounded-box">Rounded box</div>
    <div class="box more-rounded-box">Even more rounded box</div>
  </div>
  
  <h2>Extends</h2>
  
  <p>Extends lets you share a set of css properties between selectors. In this example all messages share the same style except for the background color.</p>
  
  <div class="example-extends">
    <div class="message">This is a normal message</div>
    <div class="error">This is an error message!</div>
    <div class="success">This is a succes message :)</div>
  </div>
  
  <h2>Maps</h2>
  
  <p>Maps let us group a data in key: value form, where you look at the key to get the value. In this examples the text colors are taken from a map.</p>
  
  <div class="example-maps">
    <div class="error">This is an error message</div>
    <div class="success">This is a success message</div>
  </div>
  
  <h2>Functions</h2>
  
  <p>Sass allow us to declare functions, pass arguments to them and get the result in return. The example is similar to the one above but we get the colors from the map using a function called 'palette'.</p>
  
  <div class="example-functions">
    <div class="error">This is an error message</div>
    <div class="success">This is a success message</div>
  </div>

</div>
```

```css
// Variables
// This will be used on most examples.

$color-blue: #2196f3;
$color-red: #f44336;
$color-green: #2ecc71;

$font-size-large: 22px;

// Examples

.example-variables {
  color: $color-blue;
  font-size: $font-size-large;
}

.example-operators {
  $box-width: 50px;
  span {
    vertical-align: middle;
  }
  .operator {
    font-size: $font-size-large;
    font-weight: 700;
  }
  .box {
    margin-bottom: 12px;
    line-height: 100px;
    text-align: center;
    display: inline-block;
    width: $box-width;
    height: 100px;
    background-color: gray;
  }
  .result-box {
    width: $box-width + $box-width;
  }
  .color {
    width: 100px;
    height: 100px;
    display: inline-block;
    border-radius: 50%;
  }
  .primary-color {
    background-color: $color-red;
  }
  .secondary-color {
    background-color: $color-blue;
  }
  .result {
    background-color:  $color-red - $color-blue;
  }
}

.example-nesting {
  ul li {
    color: $color-blue;
    ul li {
      color: $color-red;
    }
  }
}

@mixin border-radius($radius) {
  border-radius: $radius;
}

.example-mixins {
  .box {
    display: inline-block;
    vertical-align: middle;
    text-align: center;
    width: 100px;
    height: 100px;
    padding-top: 1rem;
    background-color: gray;
  }
  .rounded-box {
    @include border-radius(5px);
  }
  .more-rounded-box {
    @include border-radius(20px);
  }
}

.example-extends {
  .message {
    padding: 1em;
    margin-bottom: 1em;
    background-color: gray;
    text-align: center;
  }
  .success {
    @extend .message;
    background-color: $color-green;
  }
  .error {
    @extend .message;
    background-color: $color-red;
  }
}

.example-maps {
  $colors: (red: $color-red, green: $color-green);
  .error {
    color: map-get($colors, red);
  }
  .success {
    color: map-get($colors, green);
  }
}

.example-functions {
  $colors: (red: $color-red, green: $color-green);
  @function palette($color) {
    @return map-get($colors, $color);
  }
  .error {
    color: palette(red);
  }
  .success {
    color: palette(green);
  }
}

// General Styles

* {
  box-sizing: border-box;
}

.snippets {
  padding: 1rem;
}
```

## Credits

email: Juan Fernandez <j.fernandez@globant.com>
twitter: @NerOrange
