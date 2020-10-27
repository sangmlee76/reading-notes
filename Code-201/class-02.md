# Read 02 - Notes: HTML Text, CSS Introduction, and Basic Javascript Instructions

## HTML "Text" (HTML/CSS: Ch 2)
1. **Structural markup** are elements that you can use to describe both headings and paragraphs
2. **Semantic markups** provides extra info, such as where emphasis is placed in a sentence (e.g. quotes, acronyms)

### Structural
+ headings: `<h1> <h2> <h3> <h4> <h5> <h6> ; <h1> is largest`
+ paragraphs: `<p> </p>`
+ bold: `<b> </b>`
+ italic: `<i> </i>`
+ superscript: `<sup> </sup>`
+ subscript: `<sub> </sub>`
+ line break: `<br />`
+ horizontal rule: `<hr />`

+ **Visual editors** (e.g. dreamweaver) resemble word processors. (see p.49 for details)

### Semantic
Often used by other programs (e.g. screen readers) to add emphasis as needed. They are not meant to be used for structural purpose.

+ strong emphasis: `<strong> </stroong>`
+ emphasis: `<em> </em>`
+ paragraph quote: `<blockquote> </blockquote>`
+ inline quote: `<q> </q>`
+ abbreviation or acronym: `<abbr> </abbr>`
+ cite: `<cite> </cite>`
+ definition: `<dfn> </dfn>`
+ webpage author contact info: `<address> </address>`
+ inserted content: `<ins> </ins>`
+ deleted content: `<del> </del>`

+ strikethrough: `<s> </s>`

***

## Introducing CSS (HTML/CSS: Ch 10)
Think of each HTML element having a box around it that can be formatted

### Common formats:
+ Boxes:
  - width and height
  - borders (color, width, and style)
  - background color and images
  - position in the browser window

+ Text:
  - typeface
  - size
  - color
  - italic, bold, upper, lower, small caps

+ Specific:
  - lists
  - tables
  - forms

### CSS rules contain two parts: selector and declaration
```
p {font-family: Arial;}
```
### How to connect CSS to HTML
1. External CSS: use `<link>` element; found in `<head>` element
2. Internal CSS: found in `<head>` element; can be inline

+ Using `<link>` element:
  - use **href** attribute  to specify the path to the css file
  - **type** attribute set to **"text/css"**
  - **rel** attribute set to **"sylesheet**

+ Can use multiple CSS files. Some use one for presentation (e.g. fonts) and a separate one for layout.

+ Using `<style>` element:
  - use **type** attribute set to **"text/css**
  - if using more than 1 html page, will need to repeat `<style>` on each page (redundant and enlarges html file)

### Common CSS selectors:
+ Universal selector: `*{}`
+ Type selector: `h1, h2, h3{}`
+ Class selector: `.note{} -OR- p.note{}`
+ Id selector: `# intro{}`
(see p. 238 and 292 for details)

### CSS precedence
+ **Last rule**: among two identical selectors, the latter will take precedence
+ **Specificity**: the selector that is more specific will take precedence
+ **Important**: add *!important* after any property value to indicate it should take precedence over rules to same element

### CSS inheritance
+ Some properties are inherited (e.g. font family) and some are not (e.g. background color)
+ Can force inheritance by using *inherit* for the value of the property

Be mindful of **browser quirk** or **browser bug** -- occurs when CSS does not display as expected on a browser. Research sites (e.g. *positioniseverything.net* or *quirksmode.org*)

***

## Basic JavaScript Instructions (Javascript: Ch 2, p. 53 - 84)
+ A **statement** is an individual instruction that the computer should follow. Starts in a new line and ends with a semi-colon
+ codes surrounded by curly braces are called **code blocks**. It is used to group several statements together
+ Use **comments** to write in descriptions of what the code does, in order to document for future reference

### Variables
+ Declaring variables: `var quantity;`
+ when delcaring variables in JS, do not need to specify the data type being stored
+ Common practice to use camel case for compund words of variable names (e.g. buildingWidth)
+ Scripts temporarily stores bits of info/data in **variables**; can be thought of as short term memory since it will not persist once the browser leaves the page
+ Once a variable is declared, you can *assign* a value to it using the equal sign operator
+ The **scope** of the variable is defined as where a variable is declared within the script -- it impacts what part of the script can use it. (see p.98 for details)
+ Shorthand for creating variables (there are 4 cited from the reading but use the following 2 for now):
  - variables are declared and values are assigned in the same statement
  - variables are declared on the same line(separated by comma), then values are assigned to each
  (see p.67 for details)
+ Rules for variable naming:
  - start with a letter, $, or an underscore. Cannot start with a number
  - cannot contain dash or a period
  - cannot use a keyword or reserved word
  - case sensitive
  - use name that describes the kind of info that will be stored
  - use camel case to name varialbes with more than one word


### Data Types
+ Numeric: handles numbers; uses raw numbers
+ String: letters and other characters; uses quotes (single or double; common practice is to use single for JS) to encase. **Escaping** is used for strings when you want to use a in-kind quotation marks within the stirng quotes -- uses the backslash (\) before the quote within the quotes.
+ Boolean: true or false
+ Arrays: used when working with a list of set of values that are related. Do not need to specify quantity of values it will hold.
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

### Arithmetic operators
+ `+` : add
+ `-` : subtract
+ `/` : divide
+ `*` : multiply
+ `++` : increment (numbers only)
    - postfix operation, `x++`, the increment operator increments and returns the value **before** incrementing
    - prefix operatioin, `++x`, the increment operator increments and returns the value after incrementing
+ `--` : decrement (numbers only)
+ `%` : modulus
(see p.76-77 for details)

### String properties
- string + string = string
- string + number = string
- number + number = number
- using any other operator with 2 strings = NaN (not a number)
(see p.78-79 for details)

***

## Decisions and Loops (Javascript: Ch 4, p. 145 - 162)
+ Use flow charts to map out the logic flow within a script
+ 2 components to a decision:
  1. Evaluate expression, which returns a value (e.g. true or false)
  2. Use conditional statement on the appropriate action to take (e.g. if/then/else)

### Comparison operators
The results of these operators will be a Boolean (True/False)

+ `==` : is equal to (checks if values are same)
+ `!=` : is not equal to (checks if values are not the same)
+ `===` : strict equal to (checks both the value and the data tupe are the same)
+ `!==` : strict not equal to (checks both the value and data type are not the same)
+ `>` : greater than
+ `<` : less than 
+ `>=` : greater than or equal to
+ `<=` : less than or equal to

(see p.150 - 151 for details)

### Logical operators
+ `&&` : logical AND
   - TT -> True; TF = FT = FF -> False
   - `(2<5) && (3>=2)` returns true)
+ `||` : logical OR
   - TT = TF = FT -> True; FF -> False
   - `(2<5) || (2<1)` returns true)
+ `!` : logical NOT
   - !True -> False; !False -> True
   - `!(2<1)` returns true)
  
+ Remember, shortcut logic:
  - false && *anything* --> false
  - true || *anything* --> true

(see p.156-157 for details)

### Using IF statements
```
if (score >= 50) {
    congratulate();
}
```
### Using IF-ELSE statements
```
if (score >= 50) {
    congratulate();
} else {
    encourage();
}
```

### Assignment operators (extra)
Assignment operators are used to change/update variables (they are **different** from Arithmetic operators from Read 07 notes).
- `=` : x = y
- `+=` : x = x + y
- `-=` : x = x - y
- `*=` : x = x * y
- `/=` : x = x / y
- `%=` : x = x % y
- `**=` : x = x ** y


***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)
