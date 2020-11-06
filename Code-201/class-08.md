# Read 08 - Notes: More CSS Layouts (HTML/CSS: Ch 15)

## CSS Layout overview (p.358-364)
+ In your own words, briefly describe the difference between **block-level** and **inline** elements. What are examples of each? (p.361)

+ In your own words, briefly describe how you would group a number of elements together. Specifically:
  - Which element would you use? 
  - What alternative elements could you use? 
  - What is the name given to the element that you use to group the elements?
  (p.362)

+ What are the **three** types of **positioning schemes** used to control the layout of a page? (p.363)

  - _________: every block-level element appears on a new line causing each item to appear lower down the page than the previous one.
  - _________: moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. Does not affect the position of surrounding elements.
  - _________: positions the element in relation to its containing element. It does not affect the position of any surrounding element). These elements move as users scroll up and down the page.
  (p. 363)

+ _________ properties indicate where a box should be positioned (e.g. tells browser how far from the top/bottom/left/right it should be placed) (p.364)
  
  - __________: a form of absolute positioning that positions the element in relation to the *browser window*, as opposed to the containing element. Do not affect positions of surrounding elements and do not move when the page scrolls.
  - __________: allows the element to be taken out of normal flow and reposition it to the *far left or right* of a containing box. It becomes a block-level element around which other content can flow.
  (p. 364)

+ Because any element moved from normal flow can overlap, the ________ property allows you to control which box appears on top. (p. 364)

## Positioning elements, in detail (p.365 - 370))

+ **Normal positioning** : each block-level element sits on top of the next one. This is the default way browsers treat HTML elements, so do not need to specify this styling in CSS. 
  - syntax: _______________
+ **Relative positioning**: moves an element in relation to where it would have been in normal flow. You can then move the element box using *offset properties (e.g. top, down, left, right)*; can use pixels or percentages.
  - syntax: _______________
+ **Absolute positioning**: the box is taken out of normal flow and no lnger affects the position of other elements on the page. *Box offset properties (e.g. top, down, left, right)* apply.
  - syntax: _______________
+ **Fixed positioning**: a type of absolute positioning that positions the element in relation to the **browser window**. If a user scrolls down the page, it stays in the exact same place (e.g. remains visible throughout the scroll)
  - syntax: _______________
+ **Z-index**: used in conjunction with relative, fixed, or absolute positioning. It uses the concept of **stacking context** to place an element on top of each other. The higher the z-index, the closer to the front (e.g. viewer).
  - syntax: _______________

## Floating elements, in detail (p.371 - 376)

+ The **float** property allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible. Must be used with a *width* property. Anything else that sits inside the containing element will flow *around* the element that is floated.
  - syntax: _______________
+ The **clear** property allows you to say that no element (within the same container) should touch the left/right hand sides of the box.
  - syntax: _______________
+ The **overflow** property used with the width property fixes a common problem that occurs when all elements within a container are floating elements.
```
{
  overflow: auto;
  width: 100%;
}
```

## Creating multi-column layouts with floats
+ This is achieved by using a `<div>` element to represent each column, and then using float property to position the elements side by side. A margin property is used to create space between the two floated boxes.

## Screen sizes
+ Always keep in mind the device screen and consider how your users will view them across different and often multiple devices
+ Understand screen resolution (and standards) and how they will impact your content. As the resolution increases, the text becomes smaller.

## Page sizes
+ Due to the variation in screen sizes and resolution, **web designers target page of 960 - 1000 pixels wide**. 
+ The area of the page that users can see without scrolling (called *"above the fold"*) is tougher to gauge; but at the same time not as critical (e.g. users usually don't mind scrolling). The generally accepted target is **570 - 600 pixels** with a hint of more content below this range (do not cram too much in this initial section, however)
+ Increasingly, adaptive/responsive design is becoming more popular to accomodate and to create a consistent UX across the variation of screen sizes and resolutions.

## Fixed and Liquid Layouts
+ Fixed width layout designs **do not** change size as the user increases or decreases the size of their browser window. Measurements tend to be given in _________.
  - advantages:
    - more accuracy in controlling size and positioning
    - more design control compared to liquid layout
    - can control lengths of lines of text regardless of size of the user's window
    - size of image will always remain the same
  - disadvantages:
    - big gaps around edge of pages
    - user's screen resolution can impact what they see if significantly different than the original design screen resolution
    - will take up more vertical space compared to liquid layout with the same content
+ Liquid layout designs stretch and contract as the user increase/decrease the size of their browser window. Measurements tend to use ___________.
  - advantages:
    - pages fill the entire browser window so no sapces around the page
    - if the user has a small window, they don't have to scroll left/right.
  - disadvantages:
    - if you do not control the width of sections of the page then the design can result in unexpected gaps around certain elements or items bunched together.
    - if user has a wide window, lines of text can be very long and hard to read.
    - if user has a narrow window, words may bunch together and end up with few words on each line.
    - if a fixed width item (e.g. images) is in a box that is too small to hold it, the image can overflow over the text.
  - **Note**: As a best practice, you can allow certain parts of the page to use liquid layout and other parts to have min/max widths.

## Fixed width layout, in detail
+ (in CSS) Setting the `<body>` element with a fixed width of **960 pixels** (`width: 960px;`) and setting the margin to `margin: 0 auto;` will fix/set the *canvas* upon which to build the page.
+ Make sure that all elements do not exceed the horizontal fixed width establish as the canvass (e.g. 960 px) 
+ When building columns and other elements, use `float: left`
+ **Note**: Sometimes an *extra HTML* element is used to contain the page, rather than fixing the width of the `<body>`. This allows the background of the browser window to have a different color than the background of the content.

## Liquid layout, in detail
+ (in CSS) Setting the `<body>` element with a width of **90%** (`width: 90%;`) and setting the margin to `margin: 0 auto;` will fix/set the *canvas* upon which to build the page. 
+ Percentages are relative so elements within the canvass will have percentages that are relative to the container.
  - for example: three columns will have each column width set to 31.3% so that it will add up to 99% (meaning that it will cover 99% of the width of the element that it's on)
+ When building columns and other elements, use `float: left`
+ Use `min-width` and `max-width` properties to help adjust for very wide and very narrow screens

## Layout grids (p.387 - 394)
+ Benefits:
  - creates continuity between different pages which may use different design
  - helps users predict where to find information
  - makes it easier to add new content to the site consistently
  - helps people collaborate on the design in a consistent way

+ See p. 389-390 for possible layouts using 960px, 12 volumn grid
  - each column has margin set to 10px (which creates a gap of 20px between each column and 10px on the right/left edges of the page)
 
+ **CSS Frameworks**: provides the code for common tasks such as creating layout grids, styling forms, creating printer-friendly version of pages, etc. (see p. 391 - 394 for details)
  - One of the most popular uses of CSS frameworks is in creating grids to layout pages (one example of such is *960 Grid System* (available at www.960.gs)
  - 960.gs provides a style sheet that can be included in HTML pages; once linked, use classes in HTML code to build the grid layout.

## Multiple style sheets (p.395 - 396)
Some authors use multiple style sheets; for example, one will be used to control the layout and another to control format (e.g.fonts, colors, etc.)

Some will make it even more **modular** and create separate style sheets to control typography, layout, forms, tables, or even subsections of a site.

### There are 2 options for adding multiple stylesheets:
1. HTML page links to one style sheet and that stylesheet uses the `@import` rule to import other style sheets. 
2. HTML links to separate `<link>` element for each style sheet.

### @import (p.395)
Note: make sure this goes above any other rule in the style sheet (i.e. it should be at the top of your CSS style sheet)
```
@import url("tables.css");
@import url("typography.css");

... rest of CSS rules
```
The *Last rule* still applies, the stylesheet that comes last will overwright any existing duplicate styles. So, the styles in the main style sheet will overwrite any styles coming in from the imported style sheets.

### link (p.396)
+ CSS style sheets are linked from the `<head>` element in HTML. 
+ Separate `<link>` elements are provided for each style sheet. 
+ The *Last rule* still applies, the stylesheet that comes last will overwright any existing duplicate styles. 
```
<head>
  <title> My Style Sheets </title>
  <link rel="stylesheet" type="text/css" href="css/site.css" />
  <link rel="stylesheet" type="text/css" href="css/tables.css" />
  <link rel="stylesheet" type="text/css" href="css/forms.css" />
  </title>
</head>
```
Note: the styles from forms.css will have precedence in accordance with the *Last rule*.
*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)