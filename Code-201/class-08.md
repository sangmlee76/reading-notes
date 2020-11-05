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

*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)