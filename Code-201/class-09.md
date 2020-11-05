# Read 09 - Study Guide: Forms and Events

## HTML Forms (HTML/CSS: Ch 7, p.144-175)
Forms can be used to collect user information; a search box is a type of form.

### How forms work
1. User fills in a form and then triggers an action (e.g. button press) to submit the information to the server
2. The name of each **form control** is sent to the server along with the value the user entered
3. The server processes the information (uses backend language) and/or stores information in a database
4. The server creates a new page to send back to the browser based ont eh information received
+ Notes:
  - information is sent to the server using name/value pairs
  - Never change the name of a form control in a page unless you know that the code on the server will understand this new value
  - **form validation** is now more often handeled by the browser rather than a JS script. This helps reduce the work on the server and it enables users if there are any errors or issues with the form.

### Form Controls
+ There are different types of form controls that are used to collect user information. Most common ones include the following:
  - **Adding Text**
    - __________: used for a *single line* of text such as email addresses and names.
    - __________: similiar to the type used for the single line text, but the characters are masked
    - __________: for multi-line of text (e.g. messages and comments)
  - **Making Choices**
    - __________: used when a user *must select one* of a number of option.
    - __________: used when a user can *select and unselect* one or more options.
    - __________: when a user must pick one of a number of options *from a list*.
  - **Submitting Forms**
    - __________: used to submit data from your form to another web page.
    - __________: similar to above but allows you to use an image.
    - __________: allows users to upload files (e.g. images)

### Form Structure (p.151-152)
+ __________ element contains all form controls. It should always carry _________ attribute and should have both __________ and ____ attribute.
+ The __________ attribute has a value equal to the URL for the page on the server that will receive the information in the form when submitted.
+ Forms can be sent using one of two methods: __________ or ____________.
  - ___________ attribute: the values from the form are added to the end of the URL specified in the `action` attribute. Ideal for short forms or pure data retrieval from the web server (read only). If not specified, this is the default method.
  - ___________ attribute: the values are sent in HTTP headers. Ideal for long forms, file uploads, sensitive information (e.g. passowords), add/deletes information from database (read and write).
  - ______ attribute: used to identify the form distinctly from other elements.

### Form inputs 
+ _____________ element is used to create several different form controls. **The value of the _______ attribute determines what kind of input that will be created.**
+ _____________ attribute: identifies the form control and is sent along with the information they enter to the server.
+ _____________ attribute: can be used to limit thenumber of characters a user may enter into a text field.
+ _____________ element is used to create a multi-line text input.
+ _____________ element allows uswers to select one option from a list. Adding a size attribute allows more than one item from the list to be shown at once. Controls can allow multiple selection.
+ _____________ element provides ability to change the appearance of action UI.
+ _____________ element enables access by vision-impaired users.
+ _____________ element allows grouping of related form controls together inside one container.
+ _____________ element is often used with the previous element to improve UI.

### Types of inputs (with page reference)
+ Password input: `type = "password"` (p.153)
+ Radio button: `type = "radio"` (p.155)
+ Checkbox: `type = "checkbox"` (p.156)
+ File upload: `type = "file"` (p.159)
+ Submit button: `type = "submit"` (p.160)
+ Image button: `type = "image"` (p.161)
+ Hidden controls: `type = hidden"` (p.162)
+ Date: `type = "date"` (p.166)
+ Email and URL: `type = "email" and type = "url"` (p.167)
+ Search: `type = "search"` (p.168)

*****
## CSS Lists, Tables & Forms (HTML/CSS: Ch 14, p.330-357)

+ Styling bullet points (p.333 - 336):
  - `list-style-type: ` : controls the shape of the bullet point and or numbering types. Often used by odered and unodered lists
  - `list-style-image: ` : user defined bullet point
  - `list-style-position: ` : position of the bullet point with with respect to the text.'
  - `list-style` : acts as a shorthand.

+ Styling tables (p.337-340):
  - `empty-cells: ` : specifies whether an empty cell border should be shown.
  - `border-spacing: ` : controls the distance between adjacent cells.
  - `border-collapse: ` : collapses into a single shared border. Takes value of *collapse* or *separate*

+ Styling forms (p.341 - 347)
  - Text inputs
  - Submit buttons
  - Fieldsets and Legends
  - Form controls alignment tips
  - Cursor styles

******

## JS Events (JS: Ch 6, p.243 - 292)

### Core steps
1. Interactions (wit webpage) create events
  - events occur when users click/tap on a link, hover or swipe over an element, type on the keyboard, resize the window, or when the page has loaded. 
2. Events trigger code
  - when an event occurs, it can be used to trigger a particular function. 
3. Code responds to users
  - events can trigger the kinds of changes the DOM is capable of managing

### Event Types (p.246 - 247)
+ UI events
+ Keyboard events
+ Mouse events
+ Focus events
+ Form events
+ Mutation events
+ Note on terminology:
  - when an event has occurred, they have been **fired** or **raised**
  - events **trigger** function or script

### Event handling (3 steps)
1. Select the **element** node(s) you want the script to respond to
2. Indicate which **event** on the selected node(s) will trigger the response (this is called **binding** an event to a DOM)
3. State the **code** you want to run when the event occurs

### Event binding (3 options)
1. HTML event handlers (**Do not use**; bad practice but found in old code - avoid and use the other 2 options)
2. **DOM event handlers**: separates the JS from the HTML, has strong browser support. Limited because it only attaches a single function to any event - can run into errors on pages where there are multiple calls to the same function.
3. **Event listeners**: Most preferred implementation. One event can trigger multiple functions, but may not be supported by all browsers.

### Traditional DOM event handlers (p.252)

Syntax:
```
element.onevent = functionName;
```
  - element -> the DOM element to target
  - onevent -> event bound to node(s) preceded by word 'on'
  - functionName -> name of function to call (note: **NO** parenthesis after the function name)

### Event listeners (p.254)
Syntax:
```
element.addEventListener('event',functionName,[Boolean]);
```
  - element -> DOM element to target
  - 'event' -> event to bind node(s) to in quote marks
  - functionName -> name of function to call
  - Boolean -> indicates something called capture, and is usually set to false.
  - Notes:
    - If you use a named function when the event fires on your chosen DOM node, write that function first

+ Using parameters with event handlers and listeners require a workaround (see p.256-257)

### Event flow (p.260)
**Event flow** is the order in which the events fire. 

+ **Event bubbling** is when the event starts at the *most* specific and flow outward to the *least* specific. **Event capturing** is the opposite, flowing inward from the least specific to the most specific node.
+ Flow of events only really matter when your code has events handlers on an element **and** one of its ancestors or descendant elements.

### Event object (p. 262)
When an event occurs, the **event object** tells you information about the event, and the element it happened upon.

### Event delegation (p.266)


+ Changing default behavior
  - preventDefault()
  - stopPropagation()

+ Steps on using event delegation (p.268-269)

### Different types of events (p.271 - 287)
+ UI events (p.272)
  - load/unload
  - error
  - resize
  scroll
+ Focus and Blur (p.274)
+ Mouse events (p.276)
  - click, dblclick
  - mousedown, mouseup
  - mouseover, mouseout, mousemove
+ Determining position (p.278)
+ Keyboard events (p.280)
  - input
  - keydown, keypress, keyup
+ Form events (p.282)
  - submit
  - change
  - input
+ Mutation event (p.284)
  - DOMNodeInserted / DOMNodeRemoved
  - DOMSubtreeModified
  - DOMNodeINsertedIntoDocument / DOMNoeRemovedFromDocument
+ HTML 5 events (p.286)
  - DOMContentLoad
  - hashchange
  - beforeunload


*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)