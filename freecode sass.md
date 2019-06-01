**Question**:

Sass: Use @each to Map Over Items in a List
The last challenge showed how the @for directive uses a starting and ending value to loop a certain number of times. Sass also offers the @each directive which loops over each item in a list or map.

On each iteration, the variable gets assigned to the current value from the list or map.

```
@each $color in blue, red, green {
  .#{$color}-text {color: $color;}
}
```
A map has slightly different syntax. Here's an example:
```
$colors: (color1: blue, color2: red, color3: green);
@each $key, $color in $colors {
  .#{$color}-text {color: $color;}
}
```
Note that the $key variable is needed to reference the keys in the map. Otherwise, the compiled CSS would have color1, color2... in it.

Both of the above code examples are converted into the following CSS:
```
.blue-text {
  color: blue;
}

.red-text {
  color: red;
}

.green-text {
  color: green;
}

```
Write an @each directive that goes through a list: blue, black, red and assigns each variable to a .color-bg class, where the "color" part changes for each item.

Each class should set the background-color the respective color.

```scss
*******Answer*********
<style type='text/sass'>
  $colors : (color1: blue, color2: black, color3: red);
  @each $key, $color in $colors {
    .#{$color}-bg {
      background-color: $color;
    }
  }
  
  
  div {
    height: 200px;
    width: 200px;
  }
</style>

<div class="blue-bg"></div>
<div class="black-bg"></div>
<div class="red-bg"></div>
```


**Question** :

Sass: Apply a Style Until a Condition is Met with `@while`
The `@while` directive is an option with similar functionality to the JavaScript while loop. It creates CSS rules until a condition is met.

The `@for` challenge gave an example to create a simple grid system. This can also work with `@while`.

```
$x: 1;
@while $x < 13 {
  .col-#{$x} { width: 100%/12 * $x;}
  $x: $x + 1;
}
```
First, define a variable `$x` and set it to 1. Next, use the `@while` directive to create the grid system while `$x` is less than 13.

After setting the CSS rule for width, `$x` is incremented by 1 to avoid an infinite loop.


Use `@while` to create a series of classes with different font-sizes.

There should be 10 different classes from text-1 to text-10. Then set font-size to 5px multiplied by the current index number. Make sure to avoid an infinite loop!

Your code should use the `@while` directive.
Your code should set an index variable to 1 to start.
Your code should increment the counter variable.
Your .text-1 class should have a font-size of 5px.
Your .text-2 class should have a font-size of 10px.
Your .text-3 class should have a font-size of 15px.
Your .text-4 class should have a font-size of 20px.
Your .text-5 class should have a font-size of 25px.
Your .text-6 class should have a font-size of 30px.
Your .text-7 class should have a font-size of 35px.
Your .text-8 class should have a font-size of 40px.
Your .text-9 class should have a font-size of 45px.
Your .text-10 class should have a font-size of 50px.


```html
**********Answer***********
<style type='text/sass'>
  $x : 1;
  @while $x < 13 {
    .text-#{$x} { 
        font-size: 5px * $x;
        }
    $x : $x + 1;
  }
  
  
</style>

<p class="text-1">Hello</p>
<p class="text-2">Hello</p>
<p class="text-3">Hello</p>
<p class="text-4">Hello</p>
<p class="text-5">Hello</p>
<p class="text-6">Hello</p>
<p class="text-7">Hello</p>
<p class="text-8">Hello</p>
<p class="text-9">Hello</p>
<p class="text-10">Hello</p>
```

**Question**

Sass: Split Your Styles into Smaller Chunks with Partials
Partials in Sass are separate files that hold segments of CSS code. These are imported and used in other Sass files. This is a great way to group similar code into a module to keep it organized.

Names for partials start with the underscore (_) character, which tells Sass it is a small segment of CSS and not to convert it into a CSS file. Also, Sass files end with the .scss file extension. To bring the code in the partial into another Sass file, use the @import directive.

For example, if all your mixins are saved in a partial named "_mixins.scss", and they are needed in the "main.scss" file, this is how to use them in the main file:

// In the main.scss file

`@import 'mixins'`
Note that the underscore is not needed in the import statement - Sass understands it is a partial. Once a partial is imported into a file, all variables, mixins, and other code are available to use.


Write an @import statement to import a partial named _variables.scss into the main.scss file.

```scss
// *****************Answer***************
// The main.scss file
@import 'variables'



```

**Question**

Sass: Extend One Set of CSS Styles to Another Element
Sass has a feature called extend that makes it easy to borrow the CSS rules from one element and build upon them in another.

For example, the below block of CSS rules style a .panel class. It has a background-color, height and border.
```
.panel{
  background-color: red;
  height: 70px;
  border: 2px solid green;
}
```
Now you want another panel called .big-panel. It has the same base properties as .panel, but also needs a width and font-size.

It's possible to copy and paste the initial CSS rules from .panel, but the code becomes repetitive as you add more types of panels.

The extend directive is a simple way to reuse the rules written for one element, then add more for another:
```
.big-panel{
  @extend .panel;
  width: 150px;
  font-size: 2em;
}
```
The .big-panel will have the same properties as .panel in addition to the new styles.


Make a class .info-important that extends .info and also has a background-color set to magenta.

```html
*********************Answer**********
<style type='text/sass'>
  h3{
    text-align: center;
  }
  .info{
    width: 200px;
    border: 1px solid black;
    margin: 0 auto;
  }

  .info-important {
    @extend .info;
    background-color: magenta
  }
  
  
  
  
</style>
<h3>Posts</h3>
<div class="info-important">
  <p>This is an important post. It should extend the class ".info" and have its own CSS styles.</p>
</div>

<div class="info">
  <p>This is a simple post. It has basic styling and can be extended for other uses.</p>
</div>

```
