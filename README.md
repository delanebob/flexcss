# flex.css
Flex.css is a lightweight mobile first responsive framework weighing just **3KB when minified and gzipped**. It has a minimum set of features to stay lightweight and doesn't have some of the unnecessary bulk like other frameworks. This is why flexcss is great as a starting point to build on top of for your web experiences.
<br/><br/>

## Getting Started
First we include the viewport tag at the top of our webpages' in the **`<meta>`** section.
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```
<br/>

Next we include our CSS file which flex.css offers in 3 different types. Sass(Scss syntax), CSS and minified CSS.
```
flex.css/
├── css/
│   ├── core.css
│   └── min/
│       └── core.css
└── scss/
    └── core.scss
```
<br/>

### Using Sass
To use Sass, download **`scss/core.scss`** and place it in with your other Sass files. Next **`@import`** this file at the start of the main Sass file you use across all the pages you want to use flex.css on.
```css
@import 'core';
//Rest off SCSS
```

### Using CSS
To use both the CSS normal and minimised, you download either version of the **`core.css`** (minimised recommended as it's lighter). Next you link this file in the **`<meta>`** with the rest of your meta links like the example below. *Note: if you plan to use the normal and make updates to it the file, updates won't be as simple as swapping a file with the new one.*
```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Your page title</title>

    <link rel="stylesheet" href="/css/core.css">
  </head>

  <body>
      <!--
      Your HTML goes here.
      -->
  </body>
</html>
```
<br/><br/>
## Features

### Consistent foundation
Flex.css build on top of [Normalize.css](http://necolas.github.io/normalize.css/) to make HTML elements more consistent across browsers.
<br/><br/>
### Mobile first responsive grid system
Flex.css offers you **5 media queries breakpoints** & responsive grids with columns split into either **5ths** or **24ths**.
<br/><br/>

#### Breakpoints
Below you can see the various breakpoints used by flex.css with the corresponding keys for those breakpoints.

Key | Applies | Classname
--- | --- | ---
*None* | *Always* | `.flex-#`
**`sm`** | ≥568px | `.flex-sm-#`
**`md`** | ≥768px | `.flex-md-#`
**`lg`** | ≥992px | `.flex-lg-#`
**`xl`** | ≥1200px | `.flex-xl-#`
<br/>

#### Choosing 5ths or 24ths
To choose whether you want to use columns of **5ths** or **24ths** you first set the container's class to either **`.flex-5g`** for **5ths** or **`.flex-24g`** for **24ths**. Next you can specify the how many columns you want a child to use by using the classnames specified above replacing the **#** with a the number of columns like in the example below.

```html
<div class="flex-5g">
  <div class="flex-5 flex-md-2">
    ...
  </div>
  <div class="flex-5 flex-md-2">
    ...
  </div>
</div>

<div class="flex-24g">
  <div class="flex-24 flex-md-12">
    ...
  </div>
  <div class="flex-24 flex-md-10">
    ...
  </div>
</div>
```
_Note: In the example above you can see that all the classnames were used for the children. When this is the case, the element uses the next set below that breakpoint. So the children with **`<div class="flex-5 flex-md-2">...</div>`** uses **2 columns** for breakpoint **`md`** and above, but **5 columns** for everything below._
<br/><br/>

#### Spacing
You can also space out children using classes similar to the columns. You just have to add **`.flex-off-#/.flex-[key]-off-#`** to the children replacing **#** with the number of columns you want it to be spaced by. This will then apply spacing to the left of the child it is applied to like in the example below.
```html
<div class="flex-5g">
  <div class="flex-5 flex-md-2">
    ...
  </div>
  <div class="flex-5 flex-md-2 flex-md-off-1">
    ...
  </div>
</div>
```
<br/>

### Responsive images
Responsive images in flex.css offers a way to make your images shrink when there isn't enough space but won't go over their natural size and get pixelated. They can be made responsive by adding the **`.responsive`** to an **`<img>`** tag with both the **`width=""`** & **`height=""`** attributes removed.<br/>
You can also make inline SVGs responsive by removing the **`height=""`** attribute and adding the **`.responsive`** class. These can be seen in the example below.
```html
<img src="/images/example.png" alt="My lovely image" class="responsive" />

<svg xmlns="http://www.w3.org/2000/svg" width="327.67" class="responsive" viewBox="0 0 327.67 303.99">
  ...
</svg>
```
<br/>

### Responsive videos
With responsive videos in flex.css you can make videos responsive of two different aspect ratios, **16:9** and older **4:3** videos. This is available for both **embeded videos** (like youtube, vimeo, etc.) and **HTML5 video elements**.
<br/><br/>
To make a video with a ratio of **16:9** responsive, wrap either your **`<iframe>`** or **`<video>`** element inside a **`<div>`** with **`class="flex-vid"`** like the example below. To make a video with a ratio of **4:3** responsive, you do the same but use **`class="flex-vid-4x3"`** instead also shown in the example below.
```html
<div class="flex-vid">
  <iframe src="https://www.youtube.com/embed/3CgrMsjGk7k?rel=0" frameborder="0" allowfullscreen></iframe>
</div>

<div class="flex-vid-4x3">
  <iframe src="https://www.youtube.com/embed/GIXM2DF0dEM?rel=0" frameborder="0" allowfullscreen></iframe>
</div>

<div class="flex-vid">
  <video controls>
    <source src="mov_bbb.mp4" type="video/mp4">
    <source src="mov_bbb.ogg" type="video/ogg">
    Your browser does not support HTML5 video.
  </video>
</div>
```
