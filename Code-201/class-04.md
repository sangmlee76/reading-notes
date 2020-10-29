# Read 04 - Study Guide: HTML Links, CSS Layout, JS Functions

## HTML links (HTML/CSS: Ch 4)
+ ________ tags are used to create links. (p. 77)

+ Write out a generic link to the NY Timnes main page, starting with the tag. The text that the user will click on will be "NY Times Main" (p. 77)

+ What is the difference between absolute and relative URLs? When do you use both of them? (p.79)

+ (T/F) A relative URL *can* be same as a file name in one of your directories. (p.80)

+ In a file directory structure. The ________ is the top level folder. This folder contains all of the other file and folders for a website. (p. 81)

+ __________ uses the same terminology to describe the relatioinship between files and folders on a website as it is in real life (p.81)

+ The ________.html file must always be located in the root folder (p.81)

+ (T/F) A child or granchild folder is closer to the root folder than a parent or a grandparent folder. (p.82)

+ (T/F) Every page on a website has a URL except images. (p.82)

+ The URL is made up of two components: _________ followed by the ________ to the content source. (p.82)

+ (T/F) There can only be **one** *index.html* which is located in the root directory. (p.82)

+ (T/F) A *directory* is another way to refer to a 'folder'. (p.83)

+ Describe the most functional use for a relative URL. What is one main criteria for using it, with respect to file location?

+ Assign the following options to the appropriate relative link use case below: <br>
(a) `<a href="reviews.html">Reviews</a>` <br>
(b) `<a href="music/listings.html">Listings</a>` <br>
(c) `<a href="movies/dvd/reviews.html">Reviews</a>` <br>
(d) `<a href="../index.html">Home</a>` <br>
(e) `<a href="../../index.html">Home</a>` <br>

  __ linking to a file in parent folder <br>
  __ linking to a file in child folder <br>
  __ linking to a file in the same folder <br>
  __ linking to a file in grandchild folder <br>
  __ linking to a file in grandparent folder <br>
(p. 84)

+ Using the `<a>` element, write out the code that links to the following e-mail: ben@franklin.org. (p.85)

+ _______ attribute is used to open a link in a new window. It is located in the ____ element and should have the value _________. (p.86)

+ Write the code to open the following link in a new window: `www.imdb.com`. (p.86)

+ _____ attribute is used to link to a specific part of the same page. Write an example of this with just 2 lines of code, where:
  - The first line should allow the user to directly go to the footer of the page called *Resources*. 
  - The second line of the code should be the footer. 
  (p.87)

+ What, if any, is the difference in code if you were linking to a specific part of another page? (p.88)

## CSS Layout (HTML/CSS: Ch 15, with focus on p.358-364)
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


## JS Functions, Methods, and Objects (JS: Ch 3, p.86-99)

### What is a function?
- A group of statements that perform a specific task. It is reuable any time it is called.
- Functions are not always executed when a page loads, so they can be a way to *store* the steps, until the script calls it based on user input, for example.
- Invoking a function is referred to as being **called**
- Functions, with a name assigned, use curly braces ({}) to signify a block of code. No semi-colon after the curly braces.
- Input (e.g. data) that is needed to run the function is called its **parameters**.
- Input (e.g. data) that is passed into a function when it is called to satisfy the parameter requirement is called its **argument** (the data to which it refers is same, the name convention is different).
- A response (e.g. output) from a function is called a **return value**
- Anonymous functions (e.g. functions without names) execute as soon as the interpreter comes across them.

***

### How to use a function
1. Declare and calling a function
2. Getting single values out of a function

### Declaring a function
- use the keyword **function** 
- assign a function name
- write statements to achieve the desired task inside the curly braces
```
function sayHello() {
    document.write('Hello!');
}
```
### Calling a function
```
sayHello();
```
### Calling a function that need information
when you call a function with parameters, you specify input values that the function requires. They can be values or variables.
```
getArea(3,5);
or
wallWidth = 3;
wallHeight = 5;
getArea(wallWidth, wallHeight);
```
### Getting a single value out of a function
In the below code sample, the desired output is the value associated with area.
```
function calArea(width, height){
    var area = width * height;
    return area;
}
```
### Getting multiple values out of a function
Functions can return more than one value using an array. 
```
function getSize(width, height,, depth){
  var area = width * height;
  var volume = width * height * depth;
  var sizes = [area, volume];
  return sizes;
}
```
+ When a function returns an array back into HTML code, and you want to grab a single value out of the array, use array indexing (assigned to a value to obtain the value)
  - Using the example code from above:
  ```
  (in HTML)
  var areaOne = getSize(3,2,3)[0];
  var volumnOne = getSize(3,2,3)[1];
  ```
  (see p.95 for details)

### Aonymous Function and Function Expression
+ **Function expression** occurs if you put a function where the interpreter would expect to see an expression, then it is treated as an expression.
+ Function expressions typically do not have a name and is thusly called **anonymous function**
(see p.96 for details)
+ **Immediately invoked function expressions (IIFE, pronounced "iffy")** are used to avoid variable conflict. They are typically used when code needs to run only once. 
  - IIFEs are commonly used as a wrapper around a set of code
  - Any variables declared within that anonymous function are effectively protected from variables in other scripts with the same name

### Variable Scope and Memory Use
+ **Local variable (or function-level)** are those created *inside* a function. They have local (or function-level) scope.
+ Interpreter creates local variables when the function is run, and removes them as soon as the function has finished its task
+ **Global variables** are those created *outside* of a function and can be used anywhere within the script. They have global scope.
+ Global variables are stored in memory for as long as the web page is loaded into the browser. 
  - global variables take up more memory, use local variables when possible
  - if a variable in undelcared, it will be treated as a global variable (this is bad practice)
+ Variable conflict can occur between global and local variables if they have the same name. This is avoided with local variables which stay within their respective functions.


## Article: [6 reasons for paired programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)
+ What are the two roles in pair programming?

  - ________ is the programmer who is typing.
  - ________ is the programmer who guides the typing programmer.

+ _________ thinks about the big picture, what comes next, scans for typos or bugs. Can use a second computer to look up solutions and documentation. They do not write code while in this role.

+ What are the 4 fundamental skills in language acquisition?
  - _____: interpreting the vocabulary
  - _____: using the correct words to communicate
  - _____: understanding waht written language intends to convey
  - _____: producing from scratch a meaninful content

+ List the 6 reasons of pair programming (per the article)? 

+ (T/F) Some research indicates that pair programming is slightly faster and produces higher-quality code.

+ (T/F) Some research identified that pairing enhances technical skills, team communication, and workplace enjoyment

+ (T/F) Pairing creates a less engaging experirence compared to working alone becaue two programmers tend to side-track each other (e.g. Facebook, web-surfing)

+ (T/F) Pair programming boosts overall confidence of both programmers involved in it.

+ (T/F) Pair programmers should only be assigned if they have equal skill level in order to optimize learning.

+ (T/F) Pair programming often create social tensions because people fundamentally have different personalities; this often leads to programmers debating who should drive.

+ (T/F) Communication skills are far less important than technical skills; therefore, pair programming should be used to exclusively hone technical skills

+ (T/F) Once you leave Code Fellows, you will never see pair programming again. So, just suck it up and endure it for the time being.

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)