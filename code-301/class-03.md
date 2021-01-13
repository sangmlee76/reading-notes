# Read 03 - Notes: Flexbox and Templating

## [Templating with Mustache](https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2)
+ JS templating uses JSON data source to quickly and efficient render client-side templates. 
+ The template engine replaces variables and instances declared in a **template file** with actual values *at runtime*. 
+ [Mustache](http://mustache.github.com/) is a *logic-less* (no `if`, `else`, or `for` loops -- **only tags**) that can be used for HTML, config files, source code, etc.
  - [mustache.js](http://github.com/janl/mustache.js) is the JS implementaion of the template system.
  - because mustache supports various languages, server side doesn't need a separate templating system.

```
Mustache.render("Hello, {{name}}, {name: "Bob"});
// returns: Hello, Bob
```


## [A Guide to Flexbox](https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2)
+ Aimed at providing a more efficient way to layout.
+ The main idea behind the flex layout is to give the container the ability to alter its items' width/height (and order) to best fill the available space.
+ Flex containers expands items to fill available free space or shinks them to prevent overflow.
+ Flexbox layout is **direction-agnostic** (unlike block and based)

## Additional Reference:
+ [Mustache.js Official Documentation](https://github.com/janl/mustache.js)
+ [Flexbox Froggy](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)



