# Read 01 - Notes: SMACSS and Responsive Web Design

## [Scalable and Modular Architecture for CSS - SMACSS](http://smacss.com/book/) 
+ [What is SMACSS?](http://smacss.com/)SMACSS (pronounced “smacks”) is more style guide than rigid framework. 
+ SMACSS is a way to examine your design process and as a way to fit those rigid frameworks into a flexible thought process. 
+ It is an attempt to document a consistent approach to site development when using CSS.
+ Categorization of CSS - provides a structure and organization to CSS, contains 5 categories
  1. **Base** - the defaults for all the elements (e.g. single element, pseudo-class, etc.). Base styles include setting heading sizes, default link styles, default font styles, and body backgrounds.
  2. **Layout** - divide the page into sections. Layouts hold one or more modules together.
  3. **Module** - the reusable, modular parts of our design. They are the callouts, the sidebar sections, the product lists and so on.
  4. **State** - describe how our modules or layouts will look when in a particular state. Is it hidden or expanded? Is it active or inactive? They are about describing how a module or layout looks on screens that are smaller or bigger.
  5. **Theme** - similar to state rules in that they describe how modules or layouts might look. Most sites don’t require a layer of theming.

+ State change - 3 ways (class name, pseudo-class, media queries) (ref: http://smacss.com/book/state)
  1. **Class name** - change happens with JavaScript. It occurs via some interaction, be it moving the mouse around, hitting something on the keyboard, or some other event.
  2. **pseudo-class** - change is done via any number of pseudo-classes. Pseudo-classes are still limited in that we can only style changes to elements that are descendants or siblings of the element in which the pseudo-class applies.
  3. **Media queries** - 

## [Responsive Web Design](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)

+ Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop. Responsive web design is focused around providing an intuitive and gratifying experience for everyone.

+ A lot of what is covered in this lesson was first talked about by Ethan online and in his book [Responsive Web Design](https://abookapart.com/products/responsive-web-design), which is worth a read.

+ Responsive and adaptive web design are closely related, and often transposed as one in the same. Responsive generally means to react quickly and positively to any change, while adaptive means to be easily modified for a new purpose or situation, such as change. 

+ With responsive design websites continually and fluidly change based on different factors, such as viewport width, while adaptive websites are built to a group of preset factors. A combination of the two is ideal, providing the perfect formula for functional websites. 

### Flexible Layouts
+ Responsive web design is broken down into three main components, including flexible layouts, media queries, and flexible media. 

+ Flexible grids are built using relative length units, most commonly percentages or em units. These relative lengths are then used to declare common grid property values such as width, margin, or padding.

+ CSS3 introduced some new relative length units, specifically related to the viewport size of the browser or device. These new units include vw, vh, vmin, and vmax. Overall support for these new units isn’t great, but it is growing. In time they look to play a large roll in building responsive websites.
  - vw: Viewports width
  - vh: Viewports height
  - vmin: Minimum of the viewport’s height and width
  - vmax: Maximum of the viewport’s height and width

+ Flexible layouts do not advocate the use of fixed measurement units, such as pixels or inches. Reason being, the viewport height and width continually change from device to device. Website layouts need to adapt to this change and fixed values have too many constraints

+ An easy formula to help identify the proportions of a flexible layout using relative values. The formula is based around taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element.
`target ÷ context = result`

### Media Queries
+ Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example. Being able to apply uniquely targeted styles opens up a world of opportunity and leverage to responsive web design.

+ Generally speaking it is recommend to use the @media rule inside of an existing style sheet to avoid any additional HTTP requests.

+ Logical operators in media queries help build powerful expressions. There are three different logical operators available for use within media queries, including and, not, and only.

+ One of the most common media features revolves around determining a height or width for a device or browser viewport. The height and width may be found by using the height and width media features. Each of these media features may then also be prefixed with the min or max qualifiers, building a feature such as min-width or max-width.

+ Within responsive design the most commonly used features include min-width and max-width. These help build responsive websites on desktops and mobile devices equally, avoiding any confusion with device features.

### Mobile first
+ The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.

### Viewport
+ Using the viewport meta tag with either the height or width values will define the height or width of the viewport respectively. Each value accepts either a positive integer or keyword. For the height property the keyword device-height value is accepted, and for the width property the keyword device-width is accepted. Using these keywords will inherit the device’s default height and width value.

### Flexible Media
+ One quick way to make media scalable is by using the max-width property with a value of 100%. Doing so ensures that as the viewport gets smaller any media will scale down according to its containers width.


## [All about floats](https://css-tricks.com/all-about-floats/)

+ Float is a CSS positioning property. To understand its purpose and origin, we can look to print design.

+ Absolutely positioned page elements are removed from the flow of the webpage, like when the text box in the print layout was told to ignore the page wrap. Absolutely positioned page elements will not affect the position of other elements and other elements will not affect them, whether they touch each other or not.

+ Aside from the simple example of wrapping text around images, floats can be used to create entire web layouts.

+ While floats can still be used for layout, **these days, we have much stronger tools for creating layout on web pages. Namely, Flexbox and Grid.** Floats are still useful to know about because they have some abilities entirely unique to them, which is all covered in this article.

+ Clear has four valid values as well. Both is most commonly used, which clears floats coming from either direction. Left and Right can be used to only clear the float from one direction respectively. None is the default, which is typically unnecessary unless removing a clear value from a cascade. 

+ One of the more bewildering things about working with floats is how they can affect the element that contains them (their “parent” element). If this parent element contained nothing but floated elements, the height of it would literally collapse to nothing. This isn’t always obvious if the parent doesn’t contain any visually noticeable background, but it is important to be aware of.

+ If you are in a situation where you always know what the succeeding element is going to be, you can apply the clear: both; value to that element and go about your business. This is ideal as it requires no fancy hacks and no additional elements making it perfectly semantic. 
  - The Empty Div Method is, quite literally, an empty div. `<div style="clear: both;"></div>`. Sometimes you’ll see a `<br>` element or some other random element used, but div is the most common because it has no browser default styling, doesn’t have any special function, and is unlikely to be generically styled with CSS. 
  - The Overflow Method relies on setting the overflow CSS property on a parent element. If this property is set to auto or hidden on the parent element, the parent will expand to contain the floats, effectively clearing it for succeeding elements. 
  - The Easy Clearing Method uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent, you apply an additional class like “clearfix” to it. 

+ If you need text wrapping around images, there really aren’t any alternatives for float. Speaking of which, check out this rather clever technique for wrapping text around irregular shapes. But for page layout, there definitely are choices. Eric Sol right here on A List Apart has an article on Faux Absolute Positioning, which is a very interesting technique that in many ways combines the flexibility of floats with the strength of absolute positioning. CSS3 has the Template Layout Module that, when widely adopted, will prove to be the page layout technique of choice.



## Additional Resources
+ [Don't Overthink It Grids](https://css-tricks.com/dont-overthink-it-grids/)
+ [CSS Floats Explained By Riding An Escalator](https://www.freecodecamp.org/news/css-floats-explained-by-riding-an-escalator-57fa55232333/)


***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)