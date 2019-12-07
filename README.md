
# Introduction

- a scripting/programming language or a tool to addinteractivity into the websites dynamically.
- It's actually a client-side scripting language but also "JS runtime is a popular tool to power web servers."
- Popular frontend JS framewroks are ReactJS, AngularJS & backend is Node.JS

# Constants
- immutable variables i.e., variables which cannot be re-assigned new content.
- ES5 it was possible by setting object properties like writable, configurable to false.
- ES6 it is poosible by keyword **const**

# Arrow functions
- is like a regular function but syntax is short. Eg: var double = num => num * 2
- with an arrow function, the **this** binding keeps its original binding from the context. closure function does not override **this** behaviour.

# Rest parameters
- a syntax/pattern use to collects all remaining parametrs into an array.
- when we pass parametrs to the function the extra passed parametrs will be available as an array using rest operator **...rest**.
- using this we can gather any number of arguments into an array
- rest paramters must be the last paramter for function
- syntax is : **...params**
- eg: 
- function student(name, age, ...address){ // here address is an array containing all extra parameters, ['faisalabad', 'pakistan'] }
- student('tariq', 25, 'faisalabad', 'pakistan'); // 'faisalabad' & 'pakistan' will be available as an array collectively to address variable in the function.

# Spread operator
- opposite of rest parameters.
- unpacks the collected elements into single elements. Collected elements can be an array, object or string.
- using this we can spread arguments from an array/object/string
- using this we can pull any argument from array/object/string
- useful for copying array/object as const arr = [1,2,3]; const arr2 = [...arr]; // ...arr => 1, 2, 3
- syntax is : **...arr**
- eg: 
- var arr = [1, 2 ,3]; After using spread operator as ...arr we will get all arguments as 1, 2, 3.

# Destructuring Assignment 
- used to break down a complex structure into parts.
- an expression that makes it possible to pull specific/all values from array/object.
- we can also set the default values for extracted variables not present in object or array. eg: const {name, age, country='PK'}
- we can also alias the extracted variable names. eg: const {name:fullname, age:userage}
- we can also destructure an array. eg: const rgb = [255, 200, 0]; const ['red', 'green'] = rgb; // 255, 200
- eg: const {name, age} = {'name' : 'alex', 'age': 20}; // alex, 20 

# Sync vs Async operations
- Sync operations block execution untill complete while Async can execute without blocking other operations (javascript)
- Async operations are generally completed by callbacks. (AJAX)

# Promises
- A promise is an object that wraps an asynchronous operation and notifies when it's done. 
- It is an alternative of **callback** but provides more features like method-chaining & error-handling.
- use to handle the large set asynchronous result of an operation.
- three states of promise are pending, fullfilled, rejected. 
- resolved by built-in states/methods
- No callback required

# Callback
- A callback is a function that executes after another function has executed.
- When a function simply accepts another function as an argument, this contained function is known as a callback function.
- A callback is a way to make asynchronous operations more synchronous (sequential order).
- eg: setTimeout, setInterval 
- **why:** useful for event-listeners & API calls & for short asynchronous operations

# Async & Await
- concept that defines **Stop and wait until something is resolved.**
- It provides a way to maintain asynchronous processing in a more synchronous fashion. 
- **async** operation returns a promise. The promise will be resolved by one of it's state.
- **await** is only used in an async function to ensure that all promises returned in the async function are synchronized
- **why:** Synchronous capabilities, controls the behaviour & Reduces “callback hell”

# Closures
- closure is an inner function that has access to the outer (enclosing) function’s variables
- Closure is an important JavaScript pattern to give private access to a variable.
- A closure is simply a function inside another function.
- It is used when you want to extend behavior such as pass variables, methods, or arrays from an outer function to inner function.
- We can also access the context defined in outer function from inner function, but not the other way around.
- **why:** Extends behaviour, usefull when working with events.

# Generators
- Generators are function that specifies what value is yielded next time.
- eg: **function* abc(){}** 
- function* abc(){ yield 'a'; yield 'b'}; abc().next().value // a  , abc().next().value // b

# Hoisting
- Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.
- this means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local.
- this means if varibale is used first but declared later, initialization will be available to variable.
