# Read 07 - Notes: HTML Tables; JS Constructor Functions

## HTML Tables (HTML/CSS: Ch 6, p126 - 145
Tables use grid format to represent information.

### Basic table structure
1. Use `<table> </table>` element to create a table, the contents are listed row-by-row (like a list)
2. Use **table row**: `<tr> </tr>` to indicate the start of each row 
3. Use **table data**: `<td> <td>` to indicate each cell 
4. Use **table heading**: `<th> </th>` to indicate table heading - works for both row and column headings. Note: for empty cells, still need to use `<th>` or `<td>` to render the table properly. (p. 132)
5. Formatting tables:
  - use `<thead>` for table heading
  - use `<tbody>` for table body
  - use `<tfoot>` for table footer


### Special table formats
+ Spanning columns (see p.133)
+ Spanning rows (see p.134)
+ Long tables (see p.135)
+ Old Code: width and spacing (p.137)
+ Old Code: border and background (p.138)

***

## Functions, Methods, and Objects (JS: p.106 - 144))
Obj constructors use a function as a **template** for creating objects.
 
### Creating and updating objects and its properties
+ The `new` keyword and the obj constructor creates a **blank** object. You can then add properties and methods to the object.
```
var hotel = new Object();   //creates  a new object, for empty objects use: var hotel = {}

//adds properties
hotel.name = 'Quay';        //each property ends with a ;
hotel.rooms = 40;
hotel.booked = 25;

//adds a method
hotel.checkAvailability = function() {      
  return this.rooms - this.booked;
};
```
+ Update the properties of an object (but not its method) using square bracket syntax.
```
hotel ['name'] = 'Park';

// delete property --> delete hotel.name;
// clearing the value of a property --> hotel.name = '';
```

### Creating many object constructors
+ Use to create several objects that represent similar things. 

+ Steps (p.108 - 109):
  1. Create an object with properties and methods (note that each statemtn that creates a new property or method or this obj ends in a **semicolon**, not a comma as in an obj literal)
  2. Create instances of the obj using the constructor function. Use the `new` keyword followed by a call to the *template** function creates a new obj.
  3. The properties of each object are given as **arguments** to the function.
```
  Using template:

  function Hotel(name, rooms, booked) {
    this.name = name;
    this.rooms = rooms;
    this.booked = booked;
    this.checkAvailability = function() {
      return this.rooms - this.booked;
    };
  }

  Create new objects:
  
  var quayHotel = new Hotel('Quay', 40, 25);
  var parkHotel = new Hotel('Park', 120, 77);

// new objs quayHotel and parkHotel have been created with the properties shown in the arguments.
```

+ See arrays and objects details on p.118-119

### Built-in objects (p. 120 - 139)
An **object model** is a group of objects, each of which represent related things from the real world. Together they form a model of something larger.

+ 3 Types:
  1. **Browser object model**: contains objects that represent the current browser window or tab (e.g. browser history, device screen) (p. 124 - 125 for details)
  2. **Document object model**: uses objects to create a representation of the current page. (p.126 - 127 for details)
  3. **Global Javascript objects**: represent things that the JS language needs to create a model of (e.g. for dates and times)(p.128 - 139 for details)

+ There are 6 data types: (p.131)
  - String
  - Number
  - Boolean
  - Undefined
  - Null
  - Object (arrays and functions are objects)

+ Common global objects:
  - String obj (p.128)
  - Number obj (p.132)
  - Math obj (p.134)
  - Date obj (p.136)

***

## Article: [Domain Modeling](https://github.com/codefellows/domain_modeling#domain-modeling)

### JS object-oriented programming:
1. The `new` keyword **instantiates** (i.e. creates) an object.
2. The constructor function **initializes** properties inside that object using the `this` key word.
3. The object is stored in a variable for later use

+ Methods can be added to a constructor function's **prototype** (an established best practice in JS)
  - Other external links on using prototypes:
    + [Using Prototypes in Javascript](https://timkadlec.com/2008/01/using-prototypes-in-javascript/)
    + [Why use prototypes in JavaScript](https://idiallo.com/javascript/why-use-prototypes)
    + [Prototypes in JavaScript](https://www.tutorialsteacher.com/javascript/prototype-in-javascript)
    + [Object Prototypes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes)
    + [Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
    + [Prototypes in JavaScript](https://medium.com/better-programming/prototypes-in-javascript-5bba2990e04b)

+ Domain modeling is the process of creating a conceptual model for a specific problem. And a domain model that's articulated well can verify and validate your understanding of that problem.

### Tips on building domain models:
1. When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
2. Model its attributes with a constructor function that defines and initializes properties.
3. Model its behaviors with small methods that focus on doing one job well.
4. Create instances using the `new` keyword followed by a call to a constructor function.
5. Store the newly created object in a variable so you can access its properties and methods from **outside**.
6. Use the `this` variable within methods so you can access the object's properties and methods from **inside**.

*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)