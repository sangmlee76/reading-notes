# Read 06 - Study Guide: JS Object literals; The DOM

## What is an object (Ch. 3)
+ Objects group together a set of variable and functions to create a _____ of something you would recognize from the real world. 

+ In an object: variables become known as _________. (p.100)
+ ________ tells us about the object.
+ In an object: functions become known as ________.
+ ________ represent tasks that are associated with the object. 
+ An object cannot have two _____ with the same name, since it will be needed to access the corresponding value.
+ The value of a _________ can be a string, number, Boolean, array, or another object.
+ The value of a ___________ is always a function.
+ HTML uses attribute names and values. CSS uses property names and values. (p.101)

### Creating an object; literal notation
+ The object is the curly braces and their contents
+ Separate each key from its value using a __________.
+ Separate each property and method with a ___________ (except the last value).
+ The keyword '_______' is used to indicate that it is using the properties of **this** object.
+ When setting properties, strings live in _________ and arrays live in square brackets.
(see p.102 for details)

### Accessing an objectd and dot notation
+ __________ is used to access a properrty or method of an object you use the name of the object followed by a period, then the name of the property or method
+ You can also access the properties or methods of an objectd using ____________ syntax.
  - Describe 3 scenarios where this notation is most commonly used.

## DOM (document objectd model)

+ The DOM specifies how broswers should create a model of an _____ page and how _______ can access and update the contents of a webpage while it is in the browswer window.

+ (T/F) The DOM is **neither** part of HTML, nor part of JavaScript; it is a **separate** set of rules.

+ (T/F) The DOM also defines methods and properties to access **and** update each objects in this model, which in turn updates what the user **sees** in the browser.

+ (T/F) The DOM is also referred to as Application Programming Interface (API)

+ (T/F) APIs let **users( and scripts)** talk to each other. The DOM states what your script can ask the browser about the current page, and how to tell the browser to update what is being shown to the users.

+ When the browser loads a web page, it creates a model of the page in _______.

+ The DOM specifies the way in which the browser should structure this model using a __________.

### The DOM tree
+ The DOM tree consists of ____ main types of nodes.
  - ____________ node is at the top of the tree and it represents the entire page
  - ____________ nodes enable access into the DOM tree. 
  - ____________ nodes are not childrens but part of the element that carries them.
  - ____________ nodes cannot have children. This is why this node is always a new branch of the DOM tree.

### Working with a DOM tree
Accessing and updating the DOM tree involves two steps:
  1. locate the node that represents the element you want to work with.
  2. use its text content, child elements, and attributes.
 
### Accessing Elements
+ Accessing individual elements:
  - **getElementsByID()**: uses the value of an element's id attribute (should be unique to the page)
  - **querySelector()**: uses a CSS selector and returns the first matching element
  - Can select individual elements by traversing from one element to another within the DOM tree
+ Accessing multiple elements (nodelists):
  - **getElementsByClassName()**: Selects all elements that have a specific value for their class attribute
  - **getElementsByTagName()**: selects all elements that have the specified tag name
  - **querySelectorAll()**: uses a CSS selector to select all matching elements

### Working with selected elements

+ Access/update text nodes:
  - select the element (e.g. `<li`>)
  - use the `firstChild` property to get the text node
  - use the text node's only property (`nodeValue`) to get the text from the element
  - `nodeValue` lets you access or update contents of a text node

+ Work with HTML content:
  - **innerHTML**: property that allows access to child elements and text content
  - **textContent**: access to just the text content
  - ** 

 (see.pp 188 - 224 for specific commands)

 ## Article: [Understanding the problem domain is the hardest part of programming](https://simpleprogrammer.com/understanding-the-problem-domain-is-the-hardest-part-of-programming)
 + It is very difficult to learn more than one thing at once.
 + Writing code is a lot like putting together a jigsaw puzzle.  We put together code with the purpose of building components that we have taken out of the “bigger picture” of the problem domain.
 + The real world is a messy place.  Many of the problem domains we face as programmers are difficult to understand and look completely different depending on your viewpoint.
 + Understanding the problem is the most critical piece to the equation. It is very difficult to solve a problem before you know the question. 
 + Look at games (e.g. game design) and they teach a player through the different levels.
 + 

### What can you do about it?
+ Cut out cases and narrow your focus to a particular part of the problem.
+ Take a part of the problem and fully understand that part before expanding the problem domain.
+ The other choice is to become better at understanding problem domains. 
  - Talk to customers, business people, and product owners
 
*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)