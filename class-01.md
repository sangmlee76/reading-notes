# Read 01 - Notes: Introductory HTML and Javascript

## How people access the web (HTML/CSS: Intro)
+ People use **web browsers** to access websites
+ Many people run outdated versions of the web browsers so may not have access to all the latest features.
+ Data flow:
    - Web browser obtains IP address of the web server from the **Domain Name Server (DNS)**
    - Web browser receives HTML and CSS provided by the web server to render the contents of the website
    - Some web sites use Javascript or Flash to add interactivity
    - Large websites (updated daily/regularly) use a **content management system (CMS)** 
    - More complex sites can use databases to store data and use programming languages such as PHP, ASP.net, Java, or Ruby on the web server
    - **Screen readers** read out the contents of the website and are increasingly becoming legal requirements (e.g. used for accesibility use cases)

***
## Structure (HTML/CSS: Ch 1)
+ Structure helps users digest information on website and hlep them navigate through the content more efficiently.
+ HTML uses **elements** to describe the structure of pages
+ **Tags** are containers -- they give information on the content between the opening and closing tags
+ **Attributes** provide additional info about the content of the element.
+ Key elements:
    - Body element : `<body>`
    - Head element: `<head>`
    - Title element: `<title>`
+ Content management systems (CMS) uses templates to control pages and sections (e.g. format). Allows a "no-code" environment to build web pages (e.g. blogging, e-commerce)
+ Reviewing website code: 
    - Use **view source** option to see source code of a web page.
    - On chrome, use **inspect** by right mouse click. Use *console* to see any error messages to assist debugging.

***
## Extra Markup (HTML/CSS: Ch 8)

### Key elements:
+ Doctype declaration - declaration to tell a browser which version of HTML the page is using: 
```
<!DOCTYPE html>
```

+ Comments in html - notes/documentation for organization - not executed as code:
```
<!-- comment -->
```

+ ID attribute - used to uniquely (cannot be used elsewhere within the html doc) id an element: 
```
<p id="id name"></p>
```

+ Class attribute - used for identifying several elements:
```
<p class="business"></p> or <p class="business size"></p> (for multiple class designation)
```

+ Block elements - elements that *start on a new line* in the browser window:
```
<h1>, <p>, <ul>, and <li>
```

+ Inline elements - elements that appear to continue on the same line as their neighboring elemments: 
```
<a>, <b>, <em>, and <img>
```

+ Grouping text and elements (block): 
```
<div>
```

+ Grouping text and elements (inline): 
```
<span>
```

+ Iframe - inserting a window of specific content in your webpage (e.g. google maps): 
```
<iframe
   src = "http://_______"
   width = "450"
   height = "350"
   frameborder = "0"
   scrolling = "no">
</iframe>
```

+ Page metadata - lives inside `<head>` elements and contains info about the webpage (see p. 191 - 192 for details): 
```
<meta>
```

+ Escape characters - used to substitute characters that have been reserved by HTML code (see p. 194 for examples). 

***

## HTML Layout (HTML/CSS - Ch 17)

### Key elements:
+ Headers and footers : `<header>` `<footer>`
+ Navigation : `<nav>`
+ Articles : `<article>`
+ Asides : `<aside>`
+ Sections : `<section>`
+ Figures : `<figure>` `<figcaption>`
+ Sectioning elements : `<div>`

***(See p. 429 for details)***

***

## Process and design (HTML/CSS - Ch 18)
1.  Identify the target user
2.  Build a site map
3.  Build a wire frame
4.  Employ design principles

### Identify the target user:
+ Who is your user?
+ Why is your user visiting your site?
+ What information will your user need?
+ How often will your user visit your site?

### Build a site map:
+ Provides structure to webpage
+ Leverage *card sorting* technique
+ Focus on **grouping**
+ Keep user's goal in mind

### Employ design principles:
+ Primary goal is clear communication to help user achieve one's goal
+ Key concepts:
  - Visual hierarchy
  - Grouping
  - Similarity
  - Navigation

***(Note: see p. 453 for details)***
***
## The ABC of Programming (Javascript - Ch 1)
A script is a series of instructions that a computer can follow to achieve a goal.

### Programming fundamentals:
1. Define the goal - what do you want the computer to accomplish for you?
2. Design the script - break down the problem by laying out the blocks of taks (and subtasks) that will be needed to achieve the goal.
3. Code each step - write out the steps using the code you want to execute.

### How computers see the world 
Computers create models of things in the read world to understand and take action.

+ Objects --> things
  - each phsyical things ia an **object**
  - there are **types** of objects
  - objects materialize as **instances**
  - **properties** of objects = characteristics; comes as name and value (as a pair)
+ Events - an action that has taken place that drives/triggers a decision or a follow-on action
+ Methods - how people/things interact with an object
  - can contain lots of instructions that together represent one task
  - it is a form of abstraction
  - retrieves or updates an object's properties <br>
  
  ***(Note: see hotel and car analogy in p. 28 - 35)***

+ Web browsers aer programs built using objects
  - Document object model (DOM) - browswer creates a model of a webpage by creating a documdnt object and creates each element in the document as an object.
+ Major browsers use a JS **interpreter** to translate instructions into ones that the computer can folloqw - each line of code is translated one-by-one <br>
***(Note: see p. 40-41 for details)***

+ When a script runs, the HTML source code is not ammended.
+ Best practice: create a separate JS file and link it using `<script>` element.
+ When a browser comes across a `<script>` element, ti stops to load the sript and checks to see if action is required
  - the `<script>` element can be placed anywhere int eh document
  - this has implications on page loading time -- in general, do not place it in the `<head>`, place it before teh `</head>/ at the end -- or use alt options).

***
[<<< Back to Main](sangmlee76.github.io/reading-notes/)
