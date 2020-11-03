# Read 03 - Notes: HTML Lists, CSS Boxes, JS Control Flow

## HTML Lists (HTML/CSS: Ch 3)
1. **Ordered lists** are 'numbered' lists
2. **Unordered lists** are bullet pointed lists
3. **Definition lists** are made up of a set of terms along with the definition for each of those terms

### Ordered lists:
```
<ol>
  <li> unwrap sandwich </li>
  <li> eat sandwich </li>
</ol>

- list item (<li>) is the actual item in the list
- use css for styling rather than directly in html
```
### Unordered lists:
```
<ul>
  <li> fruit </li>
  <li> vegetables </li>
</ul>
```
### Definition lists:
```
<dl>
  <dt> Scale </dt>
    <dd> Device used to measure weight </dd>
</dl>

- <dt>: definition term
- <dd>: definition 
```
### Nested lists:
Can put lists inside `<li>` element to create sublists
```
<ul>
  <li> Breakfast </li>
  <li> Exercise
    <ul>
      <li> aerobic </li>
      <li> anaerobic </li>
    </ul>
  </li>
</ul>
```
***
## CSS Boxes (HTML/CSS: Ch 13)
+ By default, box is sized just big enough to hold its contents

### Box height and width
+ Use **height** and **width** properties to change dimensions
  - pixels give you most granular control
  - percent box size is relative to browser window or th ebox in which it is encased
  - ems box size is relative to the text inside it
  - percent and ems are being used more to allow flexibility in cross device use cases
```
height: 300px; width: 400px;
height: 75%; width: 75%;
```
+ Limiting width:
  - **min-width**: the smallest size a box can be displayed relative to its browser window
  - **max-width**: the widest a box can be displayed relative to its browser window
+ Limiting height:
  - **min-height** and **max-height** use the same concept as min/max-width
+ Overflow content:
  - **overflow: hidden**: hides extra content
  - **overflow: scroll**: adds a scroll bar to box

### Border, Margin, and Padding
1. **Border** separates the edge of one box from another
2. **Margin** sits outside the edge of the border. The width of a margin crates gap between the borders of 2 adjacent boxes
3. **Padding** is the space between border and any content within it. Increasing padding adds to readability

### Border characteristics
+ Can change each side invidually: top right bottom left
+ **border-width** (see p.309)
+ **border-style** (see p.310)
+ **border-color** (see p.311)
+ Shorthand: can use one property to specify details; must be used in the following order [width, style, color] -->  `border: 3px dotted #0088dd;`

### Padding
+ Can change each side invidually: top right bottom left
+ It is **not** inherited; must be identified for each element (see p.313 for details)

### Margin
+ Can change each side invidually: top right bottom left
+ Shorthand: can use two values; must use in following order [right and left then top and bottom] --> `margin: 20px 10px;` (applies to padding also)

### Centering content
+ To center a box on a page, set left/right margin to **auto**
+ Make sure to set a width for your box first (otherwise it will go across the full width of the page) (see p.315 for details)

### Change inline/block
+ The **display** property converts an inline element into a block element or vice versa.
  - `display: inline;`
  - `display: block;`
  - `display: inline-block;`
  - `display: none;` (this hides an element; viewable in page source)
+ This is often used to set page navigation format (by combining `<li>` and `display`>) (see p.317 for details)

### Hiding boxes
+ **Visibility** property hides boxes but leaves a space where the lement would have been
  - `visibility: hidden;`
  - `visibility: visible;`

### Advanced CSS3 styles (p.319 - 322)
+ **border-image** applies an image to the border of any box
+ **box-shadow** adds a drop shadow around a box
+ **border-radius** provides rounded corner for boxes. It can also apply elliptical shapes.

***
## Arrays (JS: Ch 2, p.70 - 73)
+ **Arrays** are used when working with a list of set of values that are related. Do not need to specify quantity of values it will hold.
  - values are assigned to an array inside a pair of square brackets
  - arrays are created using **array literal** (preferred option)
  ```
  colors = ['white',
            'black,];
  ```
  - **array constructor uses the *new* keyword then *Array()*; the values are idnetified in parenthesis
  ```
  var colors = new Array('white',
                          'black');
  ```
  - values in arrays are accessed as if they are in a numbered list. The list starts at **zero**
  - the number assignment in an array (automatic) is called the **index** (e.g. `itemOne = colors[1]` defines the value at the second index of the array)
  - the ***length" method returns the number of items in an array (e.g. `var numColors; numColors = colors.length;`)

***
## Decision and Loops (JS: Ch 4, p.164 - 182)
+ **Switch statement** starts with a variable called the **switch value**. Each `case` indicates a possible value for this variable and the code that runs if the variable matches the value
+ Multiple IF-ELSE statements perform more slowly than switch statements
```
switch (level){
  case 'One':
    title = 'Level 1';
    break;
  case 'Two':
    title = 'Level 2';
    break;
}
```
### Type coersion and weak typing
+ JS is a **weak typing** language since the data type can change
+ **Type coersion** is changing one data type to another
+ ***Important***: when checking if 2 values are equal, use strict conditionals (e.g. `===` and `!==`)


### Truthy and Falsy values (p.167 - 168)
+ Falsy values are treated *as if* they are false
+ Truthy values are treated *as if* they are true; almost everything that is not falsy can be treated as if true
+ a **unary operator** returns a result with just one operand
```
if(document.getElementById('header'){
  //found: do something
} else{
  //not found: do something else
}

--> will return truthy if element is found and will execute first code block
```
### Short circuit values
+ Leverage truthy values (e.g. once encountered, remaining options are not executed) into developing coding best practices:
  - put code most likely to return *true* first in **OR** operations, and *false* first in **AND** operations.
  - put the options requiring most processing power last (e.g. so you may not have to run it)

### Loops
Allows repeated running of code within the loop so long as conditions are met (i.e. returns true)

### For loops
Used for a definite number of iterations. Often used in conjunction with a counter.
```
for (var i = 0; i < 10; i++){
    document.write(i);
}
```
+ **Loop counters** are use to iterate through a for loop:
  - initialization: create variable and set it to 0 (`var i = 0`)
  - condition: loop runs until this is met (`i < 10;`)
  - update (counter): iterate the counter per each run (`i++`)
+ Key loop concepts:
  - **break**: terminates loop and goes to next statement outside the loop
  - **continue**: stops current iteration, updates counter, and checks condition, then runs next iteration if true
  - **infinite loops**: the loop never stops (be sure to avoid)
  - ***important***: any variable you can define outside of the loop and that does not change *within* the loop should be defined outside of it

### While loops
Used for an indefinite number of iterations. Need to mitigate for infinite loops.
```
while (i < 10) {
    msg += i + ' x 5 = ' + (i * 5) + '<br/>';
    i++;
}
```

### Do while loops
Soimiliar to while loop but it will run the statements inside the curly braces at least once, **even if conditions are false**
```
do {
    msg += i + ' x 5 = ' + (i * 5) + '<br/>';
    i++;
} while (i < 1);
```

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)