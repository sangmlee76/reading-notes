# Read 07 - Notes: Programming with Javascript

## What is a function?
- A group of statements that perform a specific task. It is reuable any time it is called.
- Functions are not always executed when a page loads, so they can be a way to *store* the steps, until the script calls it based on user input, for example.
- Invoking a function is referred to as being **called**
- Functions, with a name assigned, use curly braces ({}) to signify a block of code. No semi-colon after the curly braces.
- Input (e.g. data) that is needed to run the function is called its **parameters**.
- Input (e.g. data) that is passed into a function when it is called to satisfy the parameter requirement is called its **argument** (the data to which it refers is same, the name convention is different).
- A response (e.g. output) from a function is called a **return value**
- Anonymous functions (e.g. functions without names) execute as soon as the interpreter comes across them.

***

## How to use a function
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
### Basic arithmetic operators

- `+` : add
- `-` : subtract
- `/` : divide
- `*` : multiply
- `++` : increment (numbers only)
    - postfix operation, `x++`, the increment operator increments and returns the value **before** incrementing
    - prefix operatioin, `++x`, the increment operator increments and returns the value after incrementing
- `--` : decrement (numbers only)
- `%` : modulus

### String properties
- string + string = string
- string + number = string
- number + number = number
- using any other operator with 2 strings = NaN (not a number)


***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)
