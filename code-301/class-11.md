# Read 11 - Notes: EJS

## [EJS tutorial from WalkThroughCode on YouTube, Videos 1-5](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt)

+ What is EJS?
  - a simple templating language that lets you generate HTML markup with plain JavaScript.

### How do you use EJS?

+ Set-up:
  1. install packages: `npm install -S express body-parser cors ejs`
  2. go through server set-up process in your `server.js` file in vscode.
  3. Create a file called `index.ejs` (within a `Views` folder)
    - set the view engine to EJS
  4. Test to see if the page loads

+ Injecting values:
  1. `<%= [variable name] %>`
    - can be placed in-line
    - can be placed in any html tags, including img
    - can be used to auto-delete

+ For loops and arrays:
  1. Create an array with target data in `server.js`
  2. Create for loop (e.g. `<% [for loop] %>`) inside the `index.ejs` file. Note that there is **no** equal sign as part of the opening EJS tag. `<%   %>` vs. `<%=   %>`.

+ If/Else statements:
  1. Create if else condition within the EJS, again there is **no** equal sign in the opening tag as this is a conditional statement.
  2. For the evaluation statement, the `<%=    %>` is used.

+ Layouts:
  1. **Not** native to EJS
  2. install package: `npm install -S express-ejs-layouts`
  3. The layout file is the wrapper
  4. Use `<%-   %>`
  5. Common use cases: nav bar, footers, reusable text that is static -- elements you want to show on every page across multiple pages.

+ Partials (sub-component of layouts):
  1. Native to EJS
  2. Use cases: nav bar, footers, reusable text that is static
  3. Use `<%- include('folder-name/file-name') %>`
  4. Make sure the folder and file are available with the data that you want displayed.


## Additional Resources:
+ [Reference: Google Books API Docs](https://developers.google.com/books/docs/v1/using#WorkingVolumes)

+ [Reference: EJS Docs](http://ejs.co/)

+ [Skim: EJS Tutorial](https://scotch.io/tutorials/use-ejs-to-template-your-node-application)
+ [Skim: Source Code for the EJS Tutorial](https://github.com/scotch-io/node-ejs)
  - Review the code that goes along with the tutorial

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)


