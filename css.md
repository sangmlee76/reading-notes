# Read 05 - Notes: Design web pages with CSS

## How CSS works
### What is CSS?
CSS allows you to create rules that control the way trhat each individual *box* (and its contents) is presented on a webpage.

### Implementing CSS
1. There are 2 methods of implementing CSS: *external* and *internal*; use ***external*** as a best practice.
2. Create a separate CSS file (typically named *styles.css*) 
3. Use the `<link>` element in the .html file to link the .css file; requires following attributes:
   + href: specifies the path to the css file.
   + type: specifies the type of document being linked to. Use ***"text/css"***
   + rel: specifies the relationship between HTML page and the file linked to. Use ***"stylesheet"***
   + Note: an HTML page can have multiple CSS style sheet links.

### CSS Rules Cascade
+ The last rule
+ The "specificity" rule
+ The "important" rule

***
## Colors

### Main ways to change color
+ RGB (ex. rgb(100, 100, 90)) - values between 0 - 255
+ Hex codes (ex. #ee3e80)
+ Color names (ex. Dark Cyan) - limited to 147 pre-defined

### Changing color in CSS3
+ RGBA - adds *opacity* as the `a` attribute (ex. rgba(100, 100, 90, 0))
+ HSL and HSLA:
    + Hue (same as color): values between 0 - 360 deg
    + Saturation (how much gray in color): expressed as % 
    + Lightness (amount of white in color; *brightness* refers to how much black in color): expressed as % (e.g. 0% = black, 100% = white)
    + Alpha: values between 0.0 - 1.0 (e.g. 0.5 = 50% transparency)

### Common 
* Foreground color - color of text. Uses RGB, hexadecimal, and color name
* Background color - same as foreground color.

***
[<<< Back to Main](sangmlee76.github.io/reading-notes/)