# Read 06a - Notes: Dynamic web pages with Javascript

## Webpage framework

1. Content layer (.html):
    + Holds the content of the webpage
    + Gives page structure and adds semantic
2. Presentation layer (.css):
    + Uses rules that state how the HTML conent is presented
3. Behavior layer (.js):
    + Control how the page behaves, by adding interactivity

## Javascript basics
1. file extension is `.js` (ex: my-script.js).
2. Each line of code is a statement and must end with a semi-colon.
```
sum = 2 + 5;
```
3. Variables must be declared.
```
var today = new Date();
```
4. Comment notation: `/* <comment> */`.

5. Linking HTML and JS, use `<script></script>`. It can be placed in any section (e.g head, body, etc.).
```
<script src="add-content.js"></script>
```
6. Best practice:  keep each language in its own file (or directory). 

7. Use of `document.write()`:
    + Is unsecure so only use in CF102
    + Takes a single string as an argument (e.g. must use concatenation)
```
greeting = "hello"
document.write('<h3>' + greeting + '</h3>');
```
***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)