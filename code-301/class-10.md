# Read 10 - Notes: The Call Stack and Debugging

## [Understanding the JavaScript Call Stack](https://medium.freecodecamp.org/understanding-the-javascript-call-stack-861e41ae61d4)
+ Javascript engine:
  - found in a hosting environment like the browser
  - single threaded interpreter with a heap and a single stack
  - browser provides web APIs such as DOM, AJAX, and Timers

+ The call stack is primarily used for function invocation (call) and is synchronous.

+ In asynchronous Javascript,the callback function is acted upon by the call stack during execution **after the call back function has been pushed to the stack** by the event loop.

+ The call stack manages function invocation.

+ A stack overflow occurs when there is a recursive without an exit point.

+ Works as a LIFO data structure principle.

+ When a function is invoked (called), the function, its parameters, and variables are **pushed into the call stack** to form a stack frame.

+ The **stack frame** is a **memory location** in the stack. The memory is cleared **when the function returns** as it is popped out of the stack.

+ **Stack overflow** occurs when there is a **recursive function** without an exit point.

## [JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

+ Reference errors
+ Syntax errors
+ Range Errors
+ Type Errors
+ [JS error reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors)

Debugging:
+ use developer console and `console.log`
+ use `breakpoints`
+ review the call stack (e.g. the path that your program has taken to reach the point of error or breaking point)
+ use `console.trace()` to see the stack at any given point

Error handling:
+ try ... catch

+ JS errors occur at runtime (because it is not a compiled language); therefore tools are available:
  - [quokka](https://quokkajs.com/)
  - [eslint](http://eslint.org/)



### [The Call Stack defined on MDN](https://developer.mozilla.org/en-US/docs/Glossary/Call_stack)




## Additional Resources
1. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)






+