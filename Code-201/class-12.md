# Read 12 - Study Guide: Docs for the HTML <canvas> Element & Chart.js

## [Easily create stunning animated charts with Charts.js](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

+ [Charts.js](https://www.chartjs.org/) is a Javascript plugin that uses HTML5's `canvas` element to draw the graph onto the page.
+ Set-up:
  1. [download charts.js](https://github.com/chartjs/Chart.js) and place it in the directory you'll be working in.
  2. create a new html page and import the sript: `<script src='Chart.min.js'></script>`
+ Sample scripts of the following charts, as implemented in HTML are availabe in this article:
  - line chart
  - pie chart
  - bar chart

****

## [Basic use of canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)

+ General syntax: `<canvas id="sample" width="150" height="150"></canvas>`
+ Note: if the rendering seems distorted, specify the `width` and `height` attributes explicitly in the `<canvas>` and not in the CSS.
+ The `<canvas>` element can be styled like any other **image** in CSS (e.g. margin, border, backgroun,etc.) -- however, they will not affect the actual drawing on the canvas
+ How it works:
  - the `<canvas>` element creates a fixed-size drawing surface that exposes one or more **rendering contexts**
  - the canvas is initially blank. To display, a script first needs to access the rendering context and draw on it. This is done via a method called `getContext()`, 
  - `getContext()` takes one parameter. For 2D graphics, use "2d" to get a `CanvasRenderingConetxt2D`.
```
var canvas = document.getElementID('sample');
var ctx = canvas.getContext('2d');
```
  - first line retrieves the node in the DOM representing the `<canvas>` element.
  - the `getContext()` moethod accesses the drawing context.

+ Build in a programmatic fallback options for the user.

****

## [Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)
+ `<canvas>` only supports two primitive shapes: rectangles and paths. 
+ Each of the following draws a rectangle:
  - A filled rectangle: `fillRect(x, y, width, height)`
  - A rectangular outline: `strokeRect(x, y, width, height)`
  - Clears the specificed rectangular area, making it fully transparent: `clearRect(x, y, width, height)`
+ Example:
```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.fillRect(25, 25, 100, 100);
    ctx.clearRect(45, 45, 60, 60);
    ctx.strokeRect(50, 50, 50, 50);
  }
}
```

### Drawing Paths
+ **Path** is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. 
+ Steps to creating shapes:
  1. First, create the path: `beginPath()`
  2. Use drawing commands to draw into the path by calling the methods that specify the paths
  3. Stroke or fill the path to render it. An optional step is to call `closePath()`
    - Note: when you call `fill()`, any open shapes are closed automatically, so you don't have to call `closePath()`. This is **not** the case when you call `stroke()`

+ Path methods:
  - `closePath()`: adds a straight line to the path
  - `stroke()`: draws the shape by stroking its outline
  - `fill()`: draws a solid shape by filling the path's content area

+ Internally, paths are stored as a list of subpaths (lines, arcs, etc.) which together form a shape. 

+ Example - Drawing a triangle:
```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 50);
    ctx.lineTo(100, 75);
    ctx.lineTo(100, 25);
    ctx.fill();
  }
}
```

### Moving the pen
+ `moveTo(x, y)` moves the pen to the coordinates specified by `x` and `y`.

+ When the canvas is initialized or `beginPath()` is called, you typically will want to use the `moveTo()` function to place the starting point somewhere else. We could also use `moveTo()` to draw unconnected paths.

### Lines
+ `lineTo(x, y)` method:
  - used to draw straight lines.
  - draws a line from the current drawing position to the position specified by `x` and `y`
  - the starting position can be changed by using `moveTo()` method
  - shapes are automatically closed when a path is filled, but not when they are stokes; therefore, must include `closePath()`.

### Arcs and circles
+ To draw arcs or circles, use: `arc()` or `arcTo()` methods
  - `arc(x, y, radius, startAngle, endAngle, anticlockwise)`: draws an arc which is centered at `(x,y)` positioin with radius `r` starting at `startAngle` and ending at `endAngle` going in the `counterclockwise` direction (a boolean value, true = counterclockwise).
  - `arcTo(x1, y1, x2, y2, radius)`: draws an arc with the given controlpoints and radius, connected to the previous point by a straight line.
  - Note: angles in the `arc` functions are measured in **radians**, not degrees. Convert degrees to radians with: `radians = (Math.PI/180)*degrees`

### Bezier and quadratic curves
+ `quadraticCurveTo(cp1x, cp1y, x, y)` draws a quadratic Bezier curve.
+ `bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)` draws a cubic Bezier curve.
+ Bezier curves are used to make speech bubbles or heart shapes

### Rectangles
+ In addition to previous methods discussed to draw directly to the canvas, we can also use `rect()` method.
+ `rect(x, y, width, height)` draws a rectangle whose top-left corner is specified by `(x,y)` with the specified `width` and `height`.
+ there is no limit to the combinations of different shapes that can be used

### Path2D objects
+ It allows you to cache or record these drawing commands.
+ The `Path2D` constructor function returns a newly instantiated `Path2D` object.
+ All the methods previously mentioned are available on `Path2D` objects.
+ The `Path2D` API also adds a way to combine paths using the `addPath` method.
+ The `Path2D` API allows the use of [SVG path data](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths) to initialize paths onyour canvas.

****
## [Applying styles and colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

### Colors
+ `fillStyle = color` : used for filling shapes
+ `strokeStyle = color` : used for shape outlines
+ Note: each new value becomes the default so if you want to change the color, will need to reassign the `fillStyle` and `strokeStyle` properties.

### Transparency
+ `globalAlpha = transparencyValue` : applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (fully transparent) to 1.0 (fully opaque); 1.0 is default.
+ It's generally more useful to set the transparency on individual shapes

### Line styles
+ `lineWidth = value` : sets the width of lines, default value is 1.0.
+ `lineCap = type` : sets the appearance of the ends of lines
  - butt: ends are squared off at the endpoints
  - round: ends are rounded
  - square: ends are squared off by adding a box with an equal width and half the height of the line's thickness
+ `lineJoin = type` : sets the appearance of the 'corners' where lines meet
  - round: rounds off the corners
  - bevel: fills an additional triangular area between the common endpoints
  - miter: connected segments are joined by extending their outside edges to connect at a single point
+ `miterLimit = value` : establishes a limit on the miter when two linesjoin at a sharp angle, to let you control how thick the junction becomes.
+ `getLineDash()` : returns the current line dash pattern array containing an even number of non-negative numbers.
+ `setLineDash(segments)` : sets the current line dash pattern
+ `lineDashOffset = value` : specifies where to start a dash array on a line

### Gradients
+ `createLinearGradient(x1, y1, x2, y2)` : creates a linear gradient object with starting points (x1, y1) and ending points (x2, y2)

+ `createRadialGradient(x1, y1, r1, x2, y2, r2)` : creates a radial gradient representing two circles, where r  = radius.

+ `gradient.addColorStop(position, color)` : creates a new color stop on the `gradient` object. Position is between 0.0 and 1.0.

### Patterns
+ `createPattern(image, type)` : creates and returns a new canvas pattern object. Where, `image` is a `CanvasImageSource` (that is, an `HTMLImageElement`, another canvas, a `<video>` element, etc. `type` is a string indicating how to use the image.

+ `type` take following values:
  - `repeat` : vertical and horizontal
  - `repeat-x` : horizontal only
  - `repeat-y` : vertical only
  - `no-repeat` : used only once

### Shadows
+ `shadowOffsetX = float` : horizontal distance the shadow extends from the object
+ `shadowOffsetY = float` : vertical distance the shadow extends from the object
+ `shadowBlur = float` : the size of the blurring effect
+ `shadowColor = color` : the color of the shadow effect

### Canvas fill rules
+ `nonzero` : details [here](http://en.wikipedia.org/wiki/Nonzero-rule)
+ `evenodd` : details [here](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule)

***
## [Drawing text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

+ `fillText(text, x, y [, maxWidth])` : fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
+ `strokeText(text, x, y [, maxWidth])` : strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

### Styling text
Additional properties which can be used to adjust the way the text gets displayed on the canvas:
+ `font = value` : the current text style being used when drawing text. This string uses the same syntax as the CSS `font` property. The default font is 10px sans-serif.
+ `textAlign = value` : text alignment setting. Possible values: `start`, `end`, `left`, `right` or `center`. The default value is `start`.
+ `textBaseline = value` : baseline alignment setting. Possible values: `top`, `hanging`, `middle`, `alphabetic`, `ideographic`, `bottom`. The default value is `alphabetic`.
+ `direction = value` : directionality. Possible values: `ltr`, `rtl`, `inherit`. The default value is `inherit`.

### Advanced text measurements
+ `measureText()` : returns a `TextMetrics` object containing the width, in pixels, that the specified text will be when drawn in the current text style.

*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)