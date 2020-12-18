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