# Read 05 - Study Guide: HTML Images; CSS Color and Text

## HTML Images (HTML/CSS: Ch 5, p.94-125)
### Adding images
+ ______ element is used to add an image to a web page. It is an empty element, and contains the following attributes:
  - ____: tells the browser where it can find the image file.
  - ____: provides the text description of the image. Use good description as it will be used by screen readers.
  - ____: can be used to provide additional information about the image. It is used to provide readers a description when they hover over the image ([reference](https://docs.oracle.com/en/cloud/saas/marketing/cm-user/Help/Posts/Tasks/CustomizingPosts/AddingTitleTagsImages.htm))
+ _____ & ______ measurements identify the image size.

### Image placement
+ There are three primary locations within an HTML file where you should place an image:
  - Before a _____________.
  - Inside the start of a _____________. In the middle of a ______________. (hint, the blanks are all the same word)
+ _________ elements always appear on a new line (e.g. `<h1>`, `<p>`).
+ _________ elements sit within a block level element and do not start on a new line (e.g. `<b`, `<em>`, `<img>`>)
+ ________ attribute was commonly used to indicate how text was to flow around an image. This is no longer used in HTML5 but may be found from time to time in old code.


### Three rules for creating images
1. Save images in the right ______.
2. Save images at the right ______.
3. Measure images in _______.

+ These are common image _______:
  - JPEG: use with images that have lots of color.
  - GIF or PNG: use with images that have flat color (filled with same color) (e.g. logos, illustration, diagrams)

+ The images you use on your website should be saved at the same _______ and _______ that you want them to appear.

+ See p.113 - 114 for details on **image dimensions** (e.g. increasing/decreasing size) and **image cropping**.

+ When sizing an image for use on the screen, always set dimension of the image in terms of ________ (not cm. or in.)
  - ________ are tiny dots on your screen
  - ________ of the screen is the number of these tiny dots on a screen
  - When creating images for print, save images at a resolution of _____ dots per inch (DPI) or higher
  - When using images for screen, only need to consider the size in terms of its **dimensions** in _______.

+ For logos, illustrations, and diagrams, designers often create images in _________ format.
+ _______ images differ from bitmap images and are ________-independent. (see p.116 for details)
+ Animated ____ show several frames of an image in sequence and therefore can be used to create simple animations. When using an animated _____, consider:  
  - each extra frame of the image increases the file size (impacts download time)

+ See p.188 for details on **transparency**

### Figure and figure caption
+ The _______ element contain images and their caption so that the two are associated.
+ The _______ element allows web authors to add a caption to an image.
+ Write an example code that incorporates how one might implement an image with a caption on a webpage using the two elements in this section. (see p.120 for details)

***
## CSS Color (HTML/CSS: Ch 11, p. 246 - 263)

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

### Basic color representation to consider
* Foreground color - color of text. Uses RGB, hexadecimal, and color name
* Background color - same as foreground color.
* Contrast - used for blending of foreground and background color to ensure text legibility (in various environments and device form factors) and to reduce eye strain.

***
## CSS Text (HTML/CSS: Ch 12, 264 - 299)
+ See p.267-268 for details on **Typeface terminology**
+ When choosing a typeface, a browser will usually only display it if it's installed on that user's *computer*
  - **font stack**: allows specifying more than one typeface with an order of preference to be used (if one is not available)
  - See p.269-270 for details on most common typeface supported by most browsers
+ See p.273 - 278 for details on all things **Fonts**.
+ `font-weight`: allows you to create bold text
+ `font-style`: allows you to create italic or oblique text
+ `text-transform`: allows you to create uppercase, lowercase, and capitalize (this allows the first letter of each word to be capitalized)
+ `text-decoration`: allows you to create underline, overline, line-through, and blink (creates a blinking animation)
+ `line-height`: sets the line-height of an entire line of text (called *leading*). It creates the vertical gap between lines of text larger. (see p.283)
+ `letter-spacing` `word-spacing`: controls the space between each word and or letter (called *kerning*)
+ `text-align`: controls the alignment of the text by setting it left, right, center, or justify
+ `vertical alignment`: is often used with inline elements and is used to align text with respect to the element. (see p.286 for details)
+ `text-indent`: allows you to indent the first line of text within an element
+ `text-shadow`: creates a drop shadow. (see p. 288 for details)
+ `:first-letter` `:first-line`: allows control to specify values for the first letter or first line of text inside an element. (see p. 289 for details)
+ `:link`: set style for links that have not been visited
+ `:visted`: set style for links that have been visited
+ `:hover` `:active` `:focus`: allows control of elements that respond to users to add interactivity (see p.291 for details)
+ Addtional **attribute selectors** are available on p.292.

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)