# Read 09 - Notes: Refactoring

## [Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

+ DEF: What is functional programming?
  - **Functional programming** is a programming paradigm — it treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

+ **Pure function** characteristics:
  - it returns the same result if given the same arguments (it is also referred as deterministic)
  - it does not cause any observable side effects

+ Pure vs impure function as an example
  - Pure: accessing parameters passed to the function to solve a calculation. No external object.
  - Impure: using a global object that was not passed as a parameter to the function to solve a calculation.

+ Other examples of impure functions; functions that:
  - read external files
  - relies on random number generator
  - have counter variables

+ DEF: **Immutable** data's state cannot change after it's created. Because ou cannot change an immutable object, if you want to make changes, you need to create a new object with the new values that you want changed.

+ With **recursion**, we keep our variables immutable.
  - Good [Wikipedia reference](https://en.wikipedia.org/wiki/Recursion_(computer_science)#Recursive_functions_and_algorithms) on recursion

+ DEF: a function consistently yields the same result for the same input, it is **referentially transparent**.
  - `pure functions + immutable data = referential transparency`

+ **Memoization** or memoisation is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again. (source: [Wikipedia: Memoization](https://en.wikipedia.org/wiki/Memoization).

+ The **filter function** expects a `true` or `false` value to determine if the element should or should not be included in the result collection.

+ The `map` method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.

+ **Reduce** is to receive a function and a collection, and return a value created by combining the items.

****
Other References:
1. [Refactoring Javascript for Readability](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec)




***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)

