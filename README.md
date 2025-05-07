
# Introduction

- a scripting/programming language or a tool to add interactivity into the websites dynamically.
- It's actually a client-side scripting language but also "JS runtime is a popular tool to power web servers."
-  it’s synchronous and single-threaded so only one code execution process can happen at any one time.
- Popular frontend JS frameworks are ReactJS, AngularJS & the backend is Node.JS

# Constants
- immutable variables i.e., variables which cannot be re-assigned new content.
- ES5 was possible by setting object properties like writable, and configurable to false.
- ES6 is poosible by keyword **const**

# Lexical Scope
- Lexical scope in JavaScript refers to the way variables are resolved based on their location in the source code. A variable’s scope is determined by the position of the code where it is defined, and it is accessible to any nested functions or blocks. This means that functions have access to variables in their own scope and the outer (lexical) scopes, but not to variables in inner scopes.

# Template string/literals
- used for string concatenation by wrapping variables by curly braces & tild operator. eg: `${firstname} ${lastname`
- also allow us to insert variables into the string like in the above example.
- used for multiple lines with keeping whitespaces.

# Function declaration & Function expression
- Both are used to write a function with the *function* keyword.
- Function declaration is as simple as writing a function & FUnction expression is assigning a function without a name to a variable/constant.
- Function declarations are hoisted while Function expression is not, which means you can call function declarations before writing a function while not function expressions.

# Arrow functions
- is like a regular function but the syntax is short. Eg: var double = num => num * 2
- with an arrow function, the **this** binding keeps its original binding from the context. closure function does not override **this** behavior.

# Rest parameters
- a syntax/pattern use to collect all remaining parameters into an array.
- when we pass parameters to the function the extra passed parameters will be available as an array using the rest operator **...rest**.
- using this we can gather any number of arguments into an array
- rest parameters must be the last parameter for the function
- syntax is : **...params**
- eg: 
- function student(name, age, ...address){ // here address is an array containing all extra parameters, ['faisalabad', 'pakistan'] }
- student('tariq', 25, 'faisalabad', 'pakistan'); // 'faisalabad' & 'pakistan' will be available as an array collectively to address variable in the function.

# Spread operator
- opposite of rest parameters.
- unpacks the collected elements into single elements. Collected elements can be an array, object or string.
- using this we can spread arguments from an array/object/string
- using this we can pull any argument from an array/object/string
- useful for copying array/object as const arr = [1,2,3]; const arr2 = [...arr]; // ...arr => 1, 2, 3
- syntax is : **...arr**
- eg: 
- var arr = [1, 2 ,3]; After using the spread operator as ...arr we will get all arguments as 1, 2, 3.

# Destructuring Assignment 
- used to break down a complex structure into parts.
- an expression that makes it possible to pull specific/all values from array/object.
- we can also set the default values for extracted variables not present in object or array. eg: const {name, age, country='PK'}
- we can also alias the extracted variable names. eg: const {name:fullname, age:userage}
- we can also destructure an array. eg: const rgb = [255, 200, 0]; const ['red', 'green'] = rgb; // 255, 200
- eg: const {name, age} = {'name' : 'alex', 'age': 20}; // alex, 20 

# Sync vs Async operations
- Sync operations block execution until complete while Async can execute without blocking other operations (javascript)
- Async operations are generally completed by callbacks. (AJAX)

# Callback
- A callback is a way to make asynchronous operations more synchronous (sequential order). A callback can either be synchronous or asynchronous.
- A callback is a function that executes after another function has been executed.
- When a function simply accepts another function as an argument, this contained function is known as a callback function.
- users avoid this because of nested callbacks (Callback Hell)
- eg: setTimeout, setInterval 
- **why:** useful for event-listeners & API calls & for short asynchronous operations

# Promises
- A promise is an object that wraps an asynchronous operation and notifies when it's done. 
- It is an alternative to **callback** but provides more features like method-chaining & error handling.
- use to handle the large set asynchronous result of an operation.
- three states of the promise are pending, fulfilled, and rejected. 
- resolved by built-in states/methods
- No callback is required

# Async & Await
- a concept that defines **Stop and wait until something is resolved.**
- It is an alternative to **Promises**
- It provides a way to maintain asynchronous processing in a more synchronous fashion. 
- It allows us to write Promise-based code as if it were synchronous, but without blocking the main thread.
- **async** operation returns a promise. The promise will be resolved by one of its states.
- **await** is only used in an async function to ensure that all promises returned in the async function are synchronized
- **why:** Synchronous capabilities, controls the behaviour & Reduces “callback hell”

# Closures
- closure is an inner function that has access to the outer (enclosing) function’s variables
- Closure is an important JavaScript pattern to give private access to a variable.
- A closure is simply a function inside another function.
- It is used when you want to extend behavior such as pass variables, methods, or arrays from an outer function to an inner function.
- We can also access the context defined in the outer function from the inner function, but not the other way around.
- **why:** Extends behavior, useful when working with events.

# Generators
- Generators are function that specifies what value is yielded next time.
- eg: **function* abc(){}** 
- function* abc(){ yield 'a'; yield 'b'}; abc().next().value // a  , abc().next().value // b
- Generators in ES6 can be used in two main scenarios:
When one wants to move out of a function, one can do so using generators, and the outer code determines when to move back into the function.
With the help of generators, one can control an asynchronous call outside the code. Most importantly, though, the next value can come in only when needed; all values do not need to come back at once

# Hoisting
- Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.
- this means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local.
- this means if a variable is used first but declared later, initialization will be available to the variable.

# Temporal Dead Zone
- TDZ is a behavior that occurs when a variable is accessed before it is initialized. It is a language construct that helps to catch errors as accessing data before initializing it is incorrect. When let and const keywords are used to declare variables a TDZ may occur

# Deferred Script
- When the page loads, HTML code parsing is paused by default till the time the script has not fully executed. this happens when the server is slow or the script is heavy, and the web page gets delayed. So by using Deferred script , scripts execution is delayed till the HTML parser rums. this helps reduce the loading time of web pages and they can be displayed faster.

# Higher-Order Functions
- Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions. In simple words, a function that accepts functions as parameters and/or returns a function is called a Higher-Order function. This is something related to Abstraction where the actions are data flow is hidden.

# Event loop & Call Stack
- In JavaScript, the event loop manages the execution of code, handling both synchronous and asynchronous operations. The call stack stores function calls and executes them in a Last In, First Out (LIFO) order. When asynchronous code (e.g., setTimeout, promises) is encountered, it’s offloaded to the callback queue once its execution context is ready.
- The event loop continuously checks the call stack and moves tasks from the callback queue to the stack when it’s empty, allowing asynchronous code to run without blocking the main thread.

# Debouncing & Throttling
- Debouncing and throttling are techniques used to optimize performance by limiting the frequency of function executions in response to events like scrolling or resizing.
  - **Debouncing** ensures that a function is only executed after a certain amount of idle time, i.e., it delays the execution until the event stops triggering for a specified time
  - e.g., for search input
  - **Throttling** limits the number of times a function can be executed in a given period, ensuring it runs at regular intervals
  - e.g., during scroll or window resizing

# Higher Order Function
- A higher-order function in JavaScript is a function that either takes one or more functions as arguments, or returns a function as its result. These functions allow for more abstract and reusable code, enabling functional programming patterns
- For example, map() and filter() are higher-order functions because they take callback functions as arguments.

# Memoization
- Memoization in JavaScript is an optimization technique that stores the results of expensive function calls and reuses them when the same inputs occur again.
- This reduces the number of computations by caching the results. Memoization is typically implemented using an object or a map to store function arguments and their corresponding results. When the function is called with the same arguments, the cached result is returned instead of recalculating it.
- This improves performance, especially for functions with repeated calls and expensive computations.

# Event Bubbling
- Consider a situation an element is present inside another element and both of them handle an event. When an event occurs in bubbling, the innermost element handles the event first, then the outer, and so on.

# call vs apply vs bind
**call**
- The call method calls a function with the provided object(this) value and individual arguments.
- It provides a new value of this function/method, you can write a method once and then inherit it in another object, without having to rewrite the method for the new object.
- If the first argument is not passed, the value of this is bound to the global object. (the first argument is always an object).
  - **Caution:** In strict mode, the value of this will be undefined. See below.
 
 ```javascript
 // Inheritance example
 
 function Product(name, price) {
  this.name = name;
  this.price = price;
}

function Food(name, price) {
  Product.call(this, name, price);
  this.category = 'food';
}

function Toy(name, price) {
  Product.call(this, name, price);
  this.category = 'toy';
}

const cheese = new Food('feta', 5);
const fun = new Toy('robot', 40);
 ```

# Other JS Basic Concepts
- **Array Shallow Copy** : A shallow copy of an object is a copy whose properties share the same references from the source object from which the copy was made.
- **Array Deep Copy** : A Deep copy of an object is a copy whose properties do not share the same references from the source object from which the copy was made.
- **Null vs Undefined** : Undefined means a variable has been declared but has yet not been assigned a value **&&** Null is an assignment value. It can be assigned to a variable as a representation of no value. 
- **Truthy vs Falsy** : a truthy value is a value that is considered true when encountered in a Boolean context **&&** A falsy (sometimes written falsey) value is a value that is considered false when encountered in a Boolean context.
  - Truthy -> if (true), if ({}), if ([]), if (42), if ("0"), if ("false"), if (new Date()), if (-42), if (12n), if (3.14), if (-3.14), if (Infinity), if (-Infinity)
  - Falsy -> if (false), if (null) , if (undefined) , if (0), if (-0), if (0n), if (NaN), if ("")

