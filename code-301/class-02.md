# Read 02 - Notes: jQuery, Events, and The DOM

## JavaScript and jQuery (Duckett pages 293-301, 306-331 and 354-357)

### What is jQuery?
+ jQuery offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.
  - **Select elements** (e.g. uses CSS style queries rather than DOM queries - which are more powerful and flexible)
  - **Perform tasks** (e.g. update DOM, animate elements, loop through elements)
  - **Handle events** (e.g. methods for event listeners)

### How does it work?

1. **Element selection**:  `jQuery()` **function** or the shorthand `$()` uses CSS-style selectors, which creates a jQuery object **that holds references to the selected elements**.

```
$('li.hot')

This selector finds all of the <li> elements with a class of 'hot'. You can also sotre this jQuery object in a variable or use methods and properties to manipulate the selected DOM node.
```

2. **jQuery methods**: jQuery methods represent tasks that you commonly need to perform with elements.
```
$('li.hot').addClass('complete');

The jQuery object (or the 'jQuery selection') here is modified by adding a new class attribute with the parameter 'complete'.
```
3. Key benefits of jQuery over DOM Query
  - cross browser
  - element selection is simpler and more accurate
  - event handling is simpler with the use of a single method
  - methods affect all the selected elements without the need to use loops
  - once you have made a selection, you can apply multiple methods to it

### jQuery Deep Dive
+ **When selecting elements using uQuery**, the jQuery object contains a reference to the the element (single or multiple); whether it returns a single or multiple elements, the jQuery object assigns an index number to each element node (like an Array) (see p.306 for details)

+ **When getting information using jQuery**, if a jQuery selection holds more than one element, using a method to extract information from the selected elements will **retrieve information from ONLY the first element** in the matched set. (see p.307 for details)

+ **When setting information using jQuery**, if a jQuery selection holds more than one element, using a method to update information in the selected elements will **update ALL of the elements** in the matched set (not just the first one, which is different behavior than getting the info)(see p.307 for details)

**NOTE**: jQuery object is an array-like object because it stores list of the elements **in the same order** that they appear in the HTML document (other ojbects do not preserve order of the properties).

**Key Insight**: For a framework on how jQuery objects store references to elements and how jQuery variables cache jQuery selections (including a high-level visual model), see p.308 - 309.

**Other Notes**: 
1. In jQuery, **implicit iteration** allows you to replicate the same rule to several elements (e.g. a loop does not neet to be used).
```
$('li.hot').addClass('favorite');

This adds a new class to the existing elements with the class values 'hot'
```
2. **Chaining** is when more than one method is used in a single line of code to execute multiple methods. Most methods to **update** the jQuery selection can be chained but methods that **retrieve** information from the DOM cannot be chaine. If one method in the chain does not work the entire line of code will not run.
```
$('li[id!="one"]').hide().delay(500).fadeIn(1400);
```
3. In modern browsers, the `.ready()` method is used to check that the page is ready for your code to work with. However, if you place your script at the end of the page before the closing `</body>` tag, the HTML will have loaded.

### Getting and Setting using jQuery (p.314 - 315)
1. Getting content (p.314)
  + `.html()` retrieves only the **HTML** inside the first element in the matched set, **along with any of its descendents**.
    + to get the value of every element, use `.each()` method (details below)
  + `.text()` returns the content from every element in the matched set, along with the text from any descendents.
    + to get the content from `<input>` or `<textarea>` elements, use the `.val()` method (details below)

2. Updating/Setting content (p.316)
+ `.html()` gives every element in the matched set the same new content; may include HTML
+ `.text()` givecs every element in the matched set the same new text content; any markup would be shown as text.
+ `.replaceWith()` replaces every element in a matched set with new content; also returns the replaced elements.
+ `.remove()` removes all of the elements in the matched set.

**Key considerations**:
+ `.html()` and `.text()` will replace the content of each element whereas `.replaceWith()` and `.remove()` replace **and remove** the elements they match (including their content and child elements).
+ `.html()` and `.replaceWith()` carry the same **security risk** as using `innerHTML` property.

3. Inserting elements (p.318)
+ Two step process:
  1. Create the new elements in a jQuery object
  ``` 
  var $newFragment = $('<li>'); OR
  var $newFragment = $('<li class="new"> item </li>');
  ```
  2. Use a method to insert the content into the page
    - **.before()**: inserts content before the selected element (e.g. before the element tag)
    - **.after()**: inserts content after the selected element (e.g. after the element tag)
    - **.prepend()**: inserts content inside the element after the opening tag
    - **.append()**: inserts content inside the element before the closing tag

4. Getting and Setting attribute values
+ `.attr()`
  - get: `$('li#one').attr('id');`
  - set: `$('li#one').attr('id', 'hot');`
+ `.removeAttr()`
  - - remove: `$('li#one').removeAttr('id');`
+ `addClass()`
+ `.removeClass()`

5. Getting and Setting CSS properties
+ The `.css()` method lets you retrieve and set the values of CSS properties
  - get: `var backgroundColor = $('li').css('background-color');`
  - set: `$('li').css('background-color': '272727');` 
  - set multiple:
    ```
    $('li').css({
      'background-color': '272727',
      'font-family': 'Courier'
    });
    ```
6. jQuery loop functionality with `.each()` (p.324)
+ `.each()` method allows you to perform one or more statements on each of the items in the selection of elements that is returned by a selector.
+ can also use contextual this with `$(this)` 

### Events using jQuery (p.326 - 331)
+ The `.on()` method is used to handle all events.
```
$('li').on('click', function () {
  $(this).addClass('complete')'
});
```
+ Event objects in jQuery works similiar to JavaScript event objects
```
$('li').on('click', function(e) {
  eventType = e.type;
});
```

### Additional references, by topic heading:
+ Effects using jQuery (p.332 - 335)
+ Traversing and filtering using jQuery (p.336)
  - `.find()` and `.closest()` both require CSS-style seletor as an argument
  - `.add()` adds new content to the items in the existing selection and places the resulting content in a new jQuery object
+ Finding items by order - using index numbers for jQuery (p.340)
+ Working with Forms using jQuery (p. 342 - 345)
+ Cutting and Copying Elements (p.346 - 347)
  - `.remove()` removes matched element from DOM
  - `.empty()` removes child nodes and descendants
  - `.clone()` creates a copy of the matched set (including descendants and text nodes)
+ Changing box dimensions (p. 348 - 349)
+ Window and page dimensions (p.350 - 351)
  - `.height()` and `width()` methods can be used to determine the dimension of **both** the browser window and the HTML documents.
  - `.scrollLeft()` and `.scrollTop()` is used to get and set the position of the **scroll bars**
  - `.offset()` and `.position()` methods are used to determine the position of elements on the page
+ Determining position of items on the page (p.352 - 353)
+ Extended jQuery reference topics (p. 354 - 361)


*****
## Article: [6 reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)
+ What are the two roles in pair programming?

  - ________ is the programmer who is typing.
  - ________ is the programmer who guides the typing programmer.

+ _________ thinks about the big picture, what comes next, scans for typos or bugs. Can use a second computer to look up solutions and documentation. They do not write code while in this role.

+ What are the 4 fundamental skills in language acquisition?
  - _____: interpreting the vocabulary
  - _____: using the correct words to communicate
  - _____: understanding what written language intends to convey
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

## Other resources
+ JavaScript and jQuery book by Jon Duckett pages 332-335
+ JavaScript and jQuery book by Jon Duckett pages 302-305

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)