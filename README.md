# NodeCourse


notes:

First-Class Functions:
  - A programming language is said to have first-class functions when it supports treating functions like any other variable
  - Functions can be assigned to variables, passed around as arguments to other functions, used as the return value of another function

Higher-Order Functions:
  - A function that takes another function as an argument, or returns a function as its return value

Callback Functions:
  - A function that is passed to another function as an argument

  - Commonly used to execute Asynchronous code
  - A callback is passed into another function as an argument, then waits for an asynchronous operation to finish, such as a setTimeout function or fetching from a server, before the callback is executed

Closures:
  - the concept of a closure in programming refers to an inner function that has access to its enclosing scope
  - when a function is defined inside another function, the inner function automatically gets access to the variables in the outer function

Node Event Loop:
  - Node.js is organized into a single-threaded event loop
  - JavaScript is single-threaded, but modern system kernals are multithreaded and can handle multiple parallel operations in background
  - Node event loop executes incoming requests, one after another
  - Whenever it needs to, will offload I/O requests to system kernel
  - When finished, system kernel will let Node know so it can queue associated callbacks and eventually execute them via event loop

  - 6 phases
    - Timer Phase 
      - event loop executes callbacks scheduled by setTimeout() or setInterval() functions
    - Pending Callbacks Phase
      - with certain system-level error callbacks (you will not use this)
    - Idle, Prepare Phase
      - used internally by Node (you will not use this)
    - Poll Phase
      - processes a queue of callbacks, once the queue is empty, will wait for handle any new requests or timers
    - Check Phase
      - handles callbacks from setImmediate() timer function when the queue in the poll phase is empty
    - Close Callbacks Phase
      - handles emitting the 'close' event if a socket or handle is closed abruptly (you will not use this)

