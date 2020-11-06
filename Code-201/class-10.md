# Read 10 - Study Guide: JS Debugging

## JS code execution -- deep dive (p.452-)
+ JS interpreter uses the concept of ____________________. This includes one **global** execution context; plus, each **function** creates a new execution context. They correspond to variable _____________.

+ Execution Context:
  - ____________: code that is in the script but not in a function. There is only one of these context in any page.
  - ____________: code that is being run within a function. Each function has its own.
  - ____________: text is executed like code in an internal funciton called eval().

+ Variable scope:
  - ____________: declared outside a function and can be used anywhere. This is the default scope if the keyword **var** is not used.
  - ____________: declared within a function and can only be used within that function.

+ When a statement needs data from another function, it _________ (or piles) the new function on top of the current task.

## Execution Context and Hoisting (p.456-457)
+ There are two phases of execution context: _________ and _________.
  - In _____________, new scope is created. Variables, functions, and arguments are created.
  - In _____________, values are assigned to variables, reference functions and their code are run, and statements are processed.

+ In the interpreter, each exectuion context has its own _____________ object. It holds the variables, functions, and parameters available within it.  Each execution context can also access its parent's _____________ object.

## Understanding Errors (p.458-461)
+ If a JS statement generates an error, then it throws an ________. The interpreter stops and looks for error-handling code.

+ Error object properties:
  - ___________: type of error
  - ___________: description
  - ___________: name of the JS file
  - ___________: location of the error in code

+ 7 built-in error objects for JS:
  - ___________: generic error
  - ___________: incorrect syntax
  - ___________: tied to reference variable that is not declared/witin scope
  - ___________: unexpected data type that cannot be coerced
  - ___________: numbers not in acceptable range
  - ___________: URI() methods used incorrectly
  - ___________: eval() function used incorrectly

+ Most common errors: 
  - ____________: caused by incorrect use of the rules of the language.
  - ____________: caused by a variable that is not declared or is out of scope.
  - ____________: caused by trying to use an object or method that does not exist.
  - ____________: caused when a function is called using numbers outside of its accepted range.

## How to deal with errors
1. __________ the script and fix the errors
2. __________ the error gracefully by using *try, catch, throw, and finally* statements.

+ Debugging workflow:
  - look at the error message and identify: line number and type of error
  - check how far the script is running
  - use breakpoints where things are going wrong
    - break down/break out parts of the code to text smaller pieces of the functionality

+ Examples of browser specific dev tools and examples are available on p.464 - 469.

+ Main debugging tool: use `console.log()` method; others are:
  - `console.info()`
  - `console.warn()`
  - `console.error()`
  - `console.group()` with `console.groupEnd()`
  - `console.table()` - outputs a table
  - `console.assert()` - test to see if a condition is met and writes to console only if expression = false.

+ See p. 476 - 479 on **Breakpoints**

## Handling exceptions
```
try {
  // try to execute this code
} catch (exception) {
  // if there is an exception, run this code
} finally {
  // this always gets executed
}

Note: often a letter 'e' is used instead of *exception* for the catch parameter.
```
+ Note: If you use continue, break, or return keyword inside a try, it will go to the finally option

+ Throwing errors: create your own error before the interpreter creates them: `throw new Error('message'); `

+ Throwing error for NaN:
  - use a *try, catch, finally*

## Debugging tips
+ Try a different browser
+ Add numbers
+ Strip it back (remove code or comment out sections)
+ Explain the code (to someone else or to self aloud)
+ Search (classic internet detective work)
+ Code playgrounds (JSBin.com, JSFiddle.com, Dablet.com; for 'show and tell': CSSDeck.com, CodePen.com)
+ Validation tools
  - http://www.jslint.com or http://www.jshint.com
  - http://www.jsonlint.com
  - jQuery debugger plugin (in Chrome store)

## Common Errors
+ Basics:
  - case sensitivity
  - variable declaration
  - variable scope
  - reserved word use
  - matching quotes
  - properly escaped quotes
  - id attribute uniqueness 
 
+ Missed/extra characters:
  - semicolon check
  - closing braces `}` and parenthesis `)`
  - no commas inside a brace (e.g. `,}`) or parenthesis (e.g. `,)`)
  - missing parameters on function calls
  - conflicts between different script files
  - undefined vs. null. `null` is for objects; `undefined` is for properties, methods, or variables

+ Data type issues:
  - using `=` rather than `==`
  - using `===` rather than `==`
  - *switch* statements
  - *replace()* method
  - *parseInt()* method

*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)