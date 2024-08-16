### JavaScript Interview Questions and Answers

#### 1. **What is the difference between `let`, `const`, and `var`?**
   - **Answer:**
     - **`var`:** Function-scoped or globally-scoped if declared outside a function. It can be redeclared and updated. Variables declared with `var` are hoisted to the top of their scope and initialized with `undefined`.
     - **`let`:** Block-scoped, cannot be redeclared within the same scope but can be updated. `let` variables are hoisted but not initialized, so accessing them before declaration results in a `ReferenceError`.
     - **`const`:** Block-scoped, cannot be redeclared or updated. `const` must be initialized during declaration. Like `let`, it is hoisted but not initialized.

#### 2. **What is a closure in JavaScript?**
   - **Answer:**
     A closure is a function that retains access to its lexical scope, even when the function is executed outside of its original scope. In simpler terms, a closure allows a function to access variables from an outer function scope even after the outer function has returned.

     **Example:**
     ```javascript
     function outerFunction() {
       const outerVariable = 'I am from outer function';
       return function innerFunction() {
         console.log(outerVariable); // 'I am from outer function'
       };
     }
     
     const inner = outerFunction();
     inner(); // Logs 'I am from outer function'
     ```

#### 3. **What is the `this` keyword in JavaScript?**
   - **Answer:**
     The `this` keyword refers to the object that is currently executing the function. Its value depends on how the function is called:
     - **Global context:** In the global execution context, `this` refers to the global object (`window` in browsers).
     - **Function context:** In regular functions, `this` refers to the object that invoked the function.
     - **Arrow functions:** In arrow functions, `this` is lexically bound, meaning it retains the value of `this` from the enclosing non-arrow function.

#### 4. **What are arrow functions, and how do they differ from regular functions?**
   - **Answer:**
     Arrow functions are a concise syntax for writing function expressions in JavaScript. They differ from regular functions in several ways:
     - **Syntax:** Arrow functions use the `=>` syntax.
     - **`this` binding:** Arrow functions do not have their own `this` context; they inherit `this` from the surrounding scope (lexical scoping).
     - **No `arguments` object:** Arrow functions do not have an `arguments` object, unlike regular functions.
     - **Cannot be used as constructors:** Arrow functions cannot be used with the `new` keyword.

     **Example:**
     ```javascript
     const regularFunction = function() {
       return this;
     };

     const arrowFunction = () => this;
     ```

#### 5. **What is event delegation in JavaScript?**
   - **Answer:**
     Event delegation is a technique where a single event listener is added to a parent element to manage events triggered by its child elements. Instead of adding individual listeners to each child element, the parent element handles the events. This is efficient and reduces memory usage.

     **Example:**
     ```javascript
     document.querySelector('#parent').addEventListener('click', function(event) {
       if (event.target && event.target.matches('.child')) {
         console.log('Child element clicked:', event.target);
       }
     });
     ```

#### 6. **Explain the concept of `hoisting` in JavaScript.**
   - **Answer:**
     Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that you can use variables and functions before they are declared in the code. However, variables declared with `var` are hoisted and initialized with `undefined`, while variables declared with `let` and `const` are hoisted but not initialized.

     **Example:**
     ```javascript
     console.log(hoistedVar); // undefined
     var hoistedVar = 'I am hoisted';
     
     console.log(hoistedLet); // ReferenceError
     let hoistedLet = 'I am not hoisted';
     ```

#### 7. **What is the `call`, `apply`, and `bind` methods in JavaScript?**
   - **Answer:**
     - **`call`:** Invokes a function with a specified `this` value and arguments passed individually.
       ```javascript
       function greet() {
         console.log(`Hello, ${this.name}`);
       }
       const person = { name: 'John' };
       greet.call(person); // 'Hello, John'
       ```
     - **`apply`:** Similar to `call`, but arguments are passed as an array.
       ```javascript
       function greet(greeting) {
         console.log(`${greeting}, ${this.name}`);
       }
       const person = { name: 'John' };
       greet.apply(person, ['Hello']); // 'Hello, John'
       ```
     - **`bind`:** Returns a new function with a specified `this` value and optional arguments. The function can be invoked later.
       ```javascript
       function greet() {
         console.log(`Hello, ${this.name}`);
       }
       const person = { name: 'John' };
       const boundGreet = greet.bind(person);
       boundGreet(); // 'Hello, John'
       ```

#### 8. **What is the difference between `==` and `===` in JavaScript?**
   - **Answer:**
     - **`==` (loose equality):** Compares two values for equality after converting them to a common type (type coercion).
     - **`===` (strict equality):** Compares two values for equality without converting them to a common type. Both the type and the value must be the same for the comparison to return `true`.

     **Example:**
     ```javascript
     console.log(1 == '1');  // true (type coercion)
     console.log(1 === '1'); // false (different types)
     ```

#### 9. **What are Promises in JavaScript?**
   - **Answer:**
     A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises have three states:
     - **Pending:** The initial state, neither fulfilled nor rejected.
     - **Fulfilled:** The operation was completed successfully.
     - **Rejected:** The operation failed.

     **Example:**
     ```javascript
     const promise = new Promise((resolve, reject) => {
       const success = true;
       if (success) {
         resolve('Operation succeeded');
       } else {
         reject('Operation failed');
       }
     });

     promise
       .then(result => console.log(result))
       .catch(error => console.error(error));
     ```

#### 10. **What is the `async/await` syntax in JavaScript?**
   - **Answer:**
     `async/await` is syntactic sugar built on top of Promises, making asynchronous code easier to write and read. An `async` function always returns a Promise, and `await` is used to wait for a Promise to resolve or reject.

     **Example:**
     ```javascript
     async function fetchData() {
       try {
         const response = await fetch('https://api.example.com/data');
         const data = await response.json();
         console.log(data);
       } catch (error) {
         console.error('Error fetching data:', error);
       }
     }

     fetchData();
     ```

These questions cover fundamental JavaScript concepts that are commonly asked in interviews. Each answer provides a clear explanation and code example to illustrate the concept.

### JavaScript Interview Questions and Answers

#### 11. **What is the difference between `map()`, `filter()`, and `reduce()` in JavaScript?**
   - **Answer:**
     - **`map()`:** Creates a new array by applying a function to each element of the original array.
       ```javascript
       const numbers = [1, 2, 3];
       const doubled = numbers.map(num => num * 2);
       console.log(doubled); // [2, 4, 6]
       ```
     - **`filter()`:** Creates a new array with elements that pass a specified test.
       ```javascript
       const numbers = [1, 2, 3, 4];
       const even = numbers.filter(num => num % 2 === 0);
       console.log(even); // [2, 4]
       ```
     - **`reduce()`:** Reduces an array to a single value by applying a function to each element and accumulating the result.
       ```javascript
       const numbers = [1, 2, 3, 4];
       const sum = numbers.reduce((acc, num) => acc + num, 0);
       console.log(sum); // 10
       ```

#### 12. **What is the purpose of `typeof` and `instanceof` operators in JavaScript?**
   - **Answer:**
     - **`typeof`:** Returns a string indicating the type of a variable or expression.
       ```javascript
       console.log(typeof 42);            // 'number'
       console.log(typeof 'hello');       // 'string'
       console.log(typeof true);          // 'boolean'
       console.log(typeof undefined);     // 'undefined'
       console.log(typeof null);          // 'object' (this is a quirk in JavaScript)
       console.log(typeof {});            // 'object'
       console.log(typeof function() {}); // 'function'
       ```
     - **`instanceof`:** Tests whether an object is an instance of a specific constructor or class.
       ```javascript
       function Person() {}
       const person = new Person();
       console.log(person instanceof Person); // true
       console.log(person instanceof Object); // true
       ```

#### 13. **Explain the concept of `prototypal inheritance` in JavaScript.**
   - **Answer:**
     Prototypal inheritance is a feature in JavaScript where objects can inherit properties and methods from other objects. Every object in JavaScript has a prototype (except for `null`), and an object can access the properties and methods defined on its prototype through the prototype chain.

     **Example:**
     ```javascript
     const animal = {
       speak() {
         console.log('Animal speaks');
       }
     };

     const dog = Object.create(animal);
     dog.bark = function() {
       console.log('Dog barks');
     };

     dog.speak(); // 'Animal speaks' (inherited from animal)
     dog.bark();  // 'Dog barks'
     ```

#### 14. **What is the `event loop` in JavaScript?**
   - **Answer:**
     The event loop is a mechanism that allows JavaScript to perform non-blocking operations by handling asynchronous events. JavaScript runs in a single-threaded environment, so the event loop is responsible for executing code, collecting and processing events, and executing queued sub-tasks (such as callbacks and promises).

     **Example of the Event Loop:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Timeout callback');
     }, 0);

     Promise.resolve().then(() => {
       console.log('Promise callback');
     });

     console.log('End');
     ```

     **Output:**
     ```
     Start
     End
     Promise callback
     Timeout callback
     ```

#### 15. **What is the difference between `null` and `undefined` in JavaScript?**
   - **Answer:**
     - **`null`:** Represents the intentional absence of any object value. It's an assignment value.
       ```javascript
       const a = null;
       console.log(a); // null
       ```
     - **`undefined`:** Indicates that a variable has been declared but has not yet been assigned a value. It is also the default return value of functions that don't explicitly return a value.
       ```javascript
       let b;
       console.log(b); // undefined
       ```

#### 16. **What is the `spread operator` (`...`) in JavaScript?**
   - **Answer:**
     The spread operator (`...`) allows an iterable (like an array or string) to be expanded into individual elements. It's used for array manipulation, object cloning, and function arguments.

     **Examples:**
     - **Expanding an Array:**
       ```javascript
       const arr = [1, 2, 3];
       const newArr = [...arr, 4, 5];
       console.log(newArr); // [1, 2, 3, 4, 5]
       ```
     - **Cloning an Object:**
       ```javascript
       const obj = { a: 1, b: 2 };
       const newObj = { ...obj, c: 3 };
       console.log(newObj); // { a: 1, b: 2, c: 3 }
       ```
     - **Function Arguments:**
       ```javascript
       const sum = (x, y, z) => x + y + z;
       const numbers = [1, 2, 3];
       console.log(sum(...numbers)); // 6
       ```

#### 17. **What are IIFEs (Immediately Invoked Function Expressions)?**
   - **Answer:**
     An IIFE is a function that is executed immediately after it is defined. It’s a common pattern used to create a local scope and avoid polluting the global namespace.

     **Example:**
     ```javascript
     (function() {
       const message = 'Hello, World!';
       console.log(message); // 'Hello, World!'
     })();
     // message is not accessible here
     ```

#### 18. **What is the difference between `call stack` and `task queue` in JavaScript?**
   - **Answer:**
     - **Call Stack:** The call stack is a mechanism for an interpreter to keep track of its place in a script. It maintains a record of all the function calls in the order in which they are to be executed. When a function is called, it is added to the stack, and when the function returns, it is removed from the stack.
     - **Task Queue (or Event Queue):** The task queue is a queue of tasks (callbacks, promises, etc.) that are ready to be executed. The event loop processes the tasks in the queue after the call stack is empty.

     **Example:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Timeout callback');
     }, 0);

     console.log('End');
     ```

     **Output:**
     ```
     Start
     End
     Timeout callback
     ```

#### 19. **Explain `debouncing` in JavaScript.**
   - **Answer:**
     Debouncing is a technique used to limit the rate at which a function is executed. It ensures that the function is only called after a certain period of inactivity. This is useful for scenarios like handling user input events (e.g., resizing, scrolling, typing).

     **Example:**
     ```javascript
     function debounce(func, delay) {
       let timeoutId;
       return function(...args) {
         clearTimeout(timeoutId);
         timeoutId = setTimeout(() => {
           func.apply(this, args);
         }, delay);
       };
     }

     const handleResize = () => {
       console.log('Window resized');
     };

     window.addEventListener('resize', debounce(handleResize, 500));
     ```

#### 20. **What is the difference between `setTimeout` and `setInterval`?**
   - **Answer:**
     - **`setTimeout`:** Executes a function after a specified delay. The function is executed only once unless called again.
       ```javascript
       setTimeout(() => {
         console.log('Executed after 2 seconds');
       }, 2000);
       ```
     - **`setInterval`:** Repeatedly executes a function at specified intervals (in milliseconds) until `clearInterval` is called.
       ```javascript
       const intervalId = setInterval(() => {
         console.log('Executed every 2 seconds');
       }, 2000);

       // To stop the interval
       clearInterval(intervalId);
       ```

These questions further explore JavaScript's core concepts, commonly asked in interviews, and provide concise answers with relevant examples.

### JavaScript Interview Questions and Answers

#### 21. **What is the difference between `var`, `let`, and `const` in JavaScript?**
   - **Answer:**
     - **`var`:**
       - Function-scoped.
       - Can be re-declared and updated.
       - Hoisted, but initialized with `undefined`.
       - May lead to issues like unexpected behavior due to hoisting.
       ```javascript
       var x = 10;
       var x = 20; // Allowed
       ```
     - **`let`:**
       - Block-scoped.
       - Cannot be re-declared within the same scope.
       - Hoisted, but not initialized (results in a `ReferenceError` if accessed before declaration).
       ```javascript
       let y = 10;
       y = 20; // Allowed
       let y = 30; // Error: y has already been declared
       ```
     - **`const`:**
       - Block-scoped.
       - Cannot be re-declared or updated (unless it's an object or array, which allows modification of properties/elements).
       - Must be initialized at the time of declaration.
       ```javascript
       const z = 10;
       z = 20; // Error: Assignment to constant variable
       ```

#### 22. **What is hoisting in JavaScript?**
   - **Answer:**
     Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their containing scope during the compilation phase. This means that variable declarations are processed before any code is executed, but only the declarations are hoisted, not the initializations.

     **Example:**
     ```javascript
     console.log(x); // undefined
     var x = 5;
     ```
     In the above example, `var x` is hoisted to the top, so the code is interpreted as:
     ```javascript
     var x;
     console.log(x); // undefined
     x = 5;
     ```

#### 23. **What are closures in JavaScript?**
   - **Answer:**
     A closure is a function that has access to its own scope, the scope of the outer function, and the global scope. Closures allow functions to retain access to variables from their containing (enclosing) scope, even after the outer function has returned.

     **Example:**
     ```javascript
     function outerFunction() {
       let outerVariable = 'I am outside!';
       
       function innerFunction() {
         console.log(outerVariable);
       }

       return innerFunction;
     }

     const myInnerFunction = outerFunction();
     myInnerFunction(); // 'I am outside!'
     ```

#### 24. **What is the difference between `==` and `===` in JavaScript?**
   - **Answer:**
     - **`==` (Abstract Equality):**
       - Compares two values for equality after converting both values to a common type (type coercion).
       - Can lead to unexpected results due to type coercion.
       ```javascript
       console.log(2 == '2'); // true
       console.log(null == undefined); // true
       ```
     - **`===` (Strict Equality):**
       - Compares two values for equality without converting them; the values must be of the same type to be considered equal.
       - Preferred for comparison as it avoids the pitfalls of type coercion.
       ```javascript
       console.log(2 === '2'); // false
       console.log(null === undefined); // false
       ```

#### 25. **What is the difference between synchronous and asynchronous programming in JavaScript?**
   - **Answer:**
     - **Synchronous Programming:**
       - Tasks are performed one after the other, and each task waits for the previous one to complete before executing.
       - Blocking in nature.
       ```javascript
       console.log('Task 1');
       console.log('Task 2');
       console.log('Task 3');
       // Output: Task 1, Task 2, Task 3
       ```
     - **Asynchronous Programming:**
       - Tasks can be performed independently of the main program flow, and the program does not wait for the task to complete before moving on to the next one.
       - Non-blocking in nature.
       ```javascript
       console.log('Task 1');
       setTimeout(() => {
         console.log('Task 2');
       }, 1000);
       console.log('Task 3');
       // Output: Task 1, Task 3, Task 2 (after 1 second)
       ```

#### 26. **What are promises in JavaScript?**
   - **Answer:**
     A promise is an object representing the eventual completion or failure of an asynchronous operation. Promises provide a way to handle asynchronous operations more effectively than callbacks, with methods like `.then()`, `.catch()`, and `.finally()`.

     **Example:**
     ```javascript
     const myPromise = new Promise((resolve, reject) => {
       let success = true;
       if (success) {
         resolve('Operation was successful');
       } else {
         reject('Operation failed');
       }
     });

     myPromise
       .then(result => console.log(result)) // 'Operation was successful'
       .catch(error => console.error(error))
       .finally(() => console.log('Promise completed'));
     ```

#### 27. **What is async/await in JavaScript?**
   - **Answer:**
     `async/await` is syntactic sugar built on top of promises. It allows you to write asynchronous code that looks and behaves more like synchronous code, making it easier to read and understand.

     - **`async`:** Declares a function as asynchronous, meaning it will return a promise.
     - **`await`:** Pauses the execution of an async function until the promise is resolved or rejected.

     **Example:**
     ```javascript
     async function fetchData() {
       try {
         let response = await fetch('https://api.example.com/data');
         let data = await response.json();
         console.log(data);
       } catch (error) {
         console.error('Error:', error);
       }
     }

     fetchData();
     ```

#### 28. **What are arrow functions in JavaScript? How do they differ from regular functions?**
   - **Answer:**
     Arrow functions are a more concise way to write functions in JavaScript. They differ from regular functions in several ways:
     - **Syntax:** Arrow functions have a shorter syntax.
     - **`this` binding:** Arrow functions do not have their own `this` context; they inherit `this` from the enclosing scope.
     - **No `arguments` object:** Arrow functions do not have an `arguments` object.
     - **Cannot be used as constructors:** Arrow functions cannot be used with the `new` keyword.

     **Example:**
     ```javascript
     // Regular function
     function add(a, b) {
       return a + b;
     }

     // Arrow function
     const add = (a, b) => a + b;
     ```

#### 29. **What are template literals in JavaScript?**
   - **Answer:**
     Template literals are a way to create strings in JavaScript, allowing for embedded expressions, multi-line strings, and string interpolation. Template literals are enclosed by backticks (\``\).

     **Example:**
     ```javascript
     const name = 'John';
     const age = 30;

     const message = `Hello, my name is ${name} and I am ${age} years old.`;
     console.log(message); // 'Hello, my name is John and I am 30 years old.'
     ```

#### 30. **What are modules in JavaScript?**
   - **Answer:**
     Modules are a way to organize and encapsulate code in JavaScript. They allow developers to split their code into smaller, reusable pieces, which can be imported and exported as needed. JavaScript modules use the `import` and `export` keywords.

     **Example:**
     - **Exporting from a module:**
       ```javascript
       // math.js
       export const add = (a, b) => a + b;
       export const subtract = (a, b) => a - b;
       ```
     - **Importing into another file:**
       ```javascript
       // main.js
       import { add, subtract } from './math';

       console.log(add(5, 3)); // 8
       console.log(subtract(5, 3)); // 2
       ```

These questions and answers delve into essential JavaScript concepts, providing detailed explanations and examples that are commonly discussed in interviews.

### JavaScript Interview Questions and Answers

#### 31. **What is event delegation in JavaScript?**
   - **Answer:**
     Event delegation is a technique in JavaScript where a single event listener is added to a parent element to manage events for multiple child elements. This approach takes advantage of event bubbling, where an event propagates up from the child element to its ancestors, allowing the parent to handle events for its descendants.

     **Example:**
     ```javascript
     document.getElementById('parent').addEventListener('click', function(event) {
       if (event.target && event.target.matches('button.classname')) {
         console.log('Button clicked:', event.target);
       }
     });
     ```
     In this example, a click event listener is added to the `parent` element, which can handle click events for any button with the class `classname` inside it.

#### 32. **What are higher-order functions in JavaScript?**
   - **Answer:**
     A higher-order function is a function that can take another function as an argument, return a function as a result, or both. Higher-order functions are a fundamental concept in functional programming.

     **Example:**
     ```javascript
     function multiplyBy(factor) {
       return function(number) {
         return number * factor;
       };
     }

     const double = multiplyBy(2);
     console.log(double(5)); // 10
     ```

#### 33. **What is the difference between `.call()`, `.apply()`, and `.bind()` in JavaScript?**
   - **Answer:**
     - **`.call()`:**
       - Invokes a function with a specified `this` value and individual arguments.
       ```javascript
       function greet(greeting) {
         console.log(`${greeting}, ${this.name}`);
       }

       const person = { name: 'John' };
       greet.call(person, 'Hello'); // 'Hello, John'
       ```
     - **`.apply()`:**
       - Similar to `.call()`, but takes arguments as an array.
       ```javascript
       greet.apply(person, ['Hi']); // 'Hi, John'
       ```
     - **`.bind()`:**
       - Returns a new function that, when invoked, has its `this` value set to the specified value, with optional arguments provided as a prefix.
       ```javascript
       const boundGreet = greet.bind(person);
       boundGreet('Hey'); // 'Hey, John'
       ```

#### 34. **What are JavaScript prototypes, and how do they work?**
   - **Answer:**
     In JavaScript, every object has a prototype, which is also an object. A prototype acts as a template from which other objects inherit properties and methods. JavaScript uses prototypes to implement inheritance.

     **Example:**
     ```javascript
     function Person(name) {
       this.name = name;
     }

     Person.prototype.sayHello = function() {
       console.log(`Hello, my name is ${this.name}`);
     };

     const john = new Person('John');
     john.sayHello(); // 'Hello, my name is John'
     ```
     In this example, the `sayHello` method is added to the `Person` prototype, allowing all instances of `Person` to use it.

#### 35. **What is the difference between `null` and `undefined` in JavaScript?**
   - **Answer:**
     - **`undefined`:**
       - Represents the absence of a value. A variable that has been declared but not initialized is `undefined`.
       ```javascript
       let x;
       console.log(x); // undefined
       ```
     - **`null`:**
       - Represents the intentional absence of any object value. It is a value that must be assigned.
       ```javascript
       let y = null;
       console.log(y); // null
       ```

#### 36. **What are IIFEs (Immediately Invoked Function Expressions) in JavaScript?**
   - **Answer:**
     An IIFE (Immediately Invoked Function Expression) is a function that is executed immediately after it is defined. IIFEs are commonly used to create a local scope, thereby avoiding polluting the global scope.

     **Example:**
     ```javascript
     (function() {
       var message = 'Hello, World!';
       console.log(message);
     })();
     // 'Hello, World!' is logged, and `message` is not accessible outside the function.
     ```

#### 37. **What is the purpose of the `Object.freeze()` method in JavaScript?**
   - **Answer:**
     `Object.freeze()` is a method that prevents modification to an object. It makes an object immutable by preventing new properties from being added, existing properties from being removed or changed, and the prototype from being modified.

     **Example:**
     ```javascript
     const obj = { name: 'John' };
     Object.freeze(obj);

     obj.name = 'Doe'; // Fails silently or throws an error in strict mode
     console.log(obj.name); // 'John'
     ```

#### 38. **How does the `event loop` work in JavaScript?**
   - **Answer:**
     The event loop is a core component of JavaScript's runtime model. It allows JavaScript to perform non-blocking operations, despite being single-threaded. The event loop continuously checks the message queue and processes the next message in the queue. If the call stack is empty, the message is processed; otherwise, it waits until the stack is clear.

     **Example:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Timeout');
     }, 0);

     console.log('End');
     // Output: Start, End, Timeout
     ```
     In this example, the `setTimeout` callback is placed in the message queue, allowing the synchronous code to finish first.

#### 39. **What is the `new` keyword in JavaScript, and how does it work?**
   - **Answer:**
     The `new` keyword is used to create an instance of an object that has a constructor function. When you use `new`, it does the following:
     1. Creates a new empty object.
     2. Sets the `this` context of the function to the new object.
     3. Links the new object to the constructor's prototype.
     4. Returns the new object.

     **Example:**
     ```javascript
     function Car(make, model) {
       this.make = make;
       this.model = model;
     }

     const myCar = new Car('Toyota', 'Corolla');
     console.log(myCar); // Car { make: 'Toyota', model: 'Corolla' }
     ```

#### 40. **What is the purpose of the `typeof` operator in JavaScript?**
   - **Answer:**
     The `typeof` operator is used to determine the data type of a given variable or expression. It returns a string indicating the type of the operand.

     **Example:**
     ```javascript
     console.log(typeof 42); // 'number'
     console.log(typeof 'Hello'); // 'string'
     console.log(typeof true); // 'boolean'
     console.log(typeof undefined); // 'undefined'
     console.log(typeof null); // 'object' (this is a known quirk)
     console.log(typeof {}); // 'object'
     console.log(typeof function() {}); // 'function'
     ```

These additional questions cover more advanced JavaScript concepts and are important for developers to understand during technical interviews.


### JavaScript Interview Questions and Answers

#### 41. **What is the difference between synchronous and asynchronous programming in JavaScript?**
   - **Answer:**
     - **Synchronous programming:**
       In synchronous programming, tasks are performed one after another, blocking the execution of the next task until the current task is complete. This can lead to delays if a task takes a long time to finish.
       ```javascript
       console.log('Start');
       for (let i = 0; i < 1e9; i++) {} // A long-running loop
       console.log('End');
       // Output: 'Start' (delay) 'End'
       ```
     - **Asynchronous programming:**
       In asynchronous programming, tasks are initiated and run independently of the main program flow, allowing other tasks to continue executing. JavaScript uses callbacks, promises, and `async/await` to handle asynchronous operations.
       ```javascript
       console.log('Start');
       setTimeout(() => {
         console.log('Timeout');
       }, 0);
       console.log('End');
       // Output: 'Start', 'End', 'Timeout'
       ```

#### 42. **What are closures in JavaScript, and how are they useful?**
   - **Answer:**
     A closure is a feature in JavaScript where an inner function has access to variables and parameters of its outer function, even after the outer function has returned. Closures are useful for creating private variables and functions.

     **Example:**
     ```javascript
     function outer() {
       let count = 0;
       return function inner() {
         count++;
         return count;
       };
     }

     const counter = outer();
     console.log(counter()); // 1
     console.log(counter()); // 2
     ```
     In this example, `inner` retains access to `count` even after `outer` has finished executing.

#### 43. **What is the `this` keyword in JavaScript?**
   - **Answer:**
     The `this` keyword in JavaScript refers to the context in which a function is executed. Its value is determined by how a function is called:
     - **In a method**: `this` refers to the object that owns the method.
     - **Alone**: `this` refers to the global object (`window` in browsers).
     - **In a function**: `this` refers to the global object (in non-strict mode) or `undefined` (in strict mode).
     - **In an event**: `this` refers to the element that received the event.
     - **With `call`, `apply`, `bind`**: `this` is explicitly defined.

     **Example:**
     ```javascript
     const person = {
       name: 'Alice',
       greet() {
         console.log(`Hello, ${this.name}`);
       }
     };

     person.greet(); // 'Hello, Alice'
     ```

#### 44. **What is the difference between `==` and `===` in JavaScript?**
   - **Answer:**
     - **`==` (Abstract Equality Operator)**: Compares two values for equality, after converting both values to a common type (type coercion).
     - **`===` (Strict Equality Operator)**: Compares two values for equality without type conversion. Both the value and the type must be the same.

     **Example:**
     ```javascript
     console.log(5 == '5');  // true (type coercion)
     console.log(5 === '5'); // false (no type coercion)
     ```

#### 45. **What are promises in JavaScript, and how do they work?**
   - **Answer:**
     A promise in JavaScript is an object that represents the eventual completion (or failure) of an asynchronous operation. Promises have three states:
     - **Pending**: Initial state, neither fulfilled nor rejected.
     - **Fulfilled**: Operation completed successfully.
     - **Rejected**: Operation failed.

     **Example:**
     ```javascript
     const promise = new Promise((resolve, reject) => {
       setTimeout(() => {
         resolve('Success!');
       }, 1000);
     });

     promise.then((value) => {
       console.log(value); // 'Success!' after 1 second
     }).catch((error) => {
       console.error(error);
     });
     ```

#### 46. **What is the difference between `map()`, `filter()`, and `reduce()` in JavaScript?**
   - **Answer:**
     - **`map()`**: Creates a new array by applying a function to each element of the original array.
       ```javascript
       const numbers = [1, 2, 3];
       const doubled = numbers.map(num => num * 2);
       console.log(doubled); // [2, 4, 6]
       ```
     - **`filter()`**: Creates a new array with all elements that pass a test implemented by a function.
       ```javascript
       const numbers = [1, 2, 3, 4];
       const evens = numbers.filter(num => num % 2 === 0);
       console.log(evens); // [2, 4]
       ```
     - **`reduce()`**: Executes a reducer function on each element of the array, resulting in a single output value.
       ```javascript
       const numbers = [1, 2, 3, 4];
       const sum = numbers.reduce((acc, num) => acc + num, 0);
       console.log(sum); // 10
       ```

#### 47. **What is the `typeof` operator and how does it work?**
   - **Answer:**
     The `typeof` operator returns a string indicating the type of the operand. It is used to check the type of a variable or expression.

     **Example:**
     ```javascript
     console.log(typeof 42);         // 'number'
     console.log(typeof 'hello');    // 'string'
     console.log(typeof true);       // 'boolean'
     console.log(typeof undefined);  // 'undefined'
     console.log(typeof null);       // 'object' (known quirk)
     console.log(typeof {});         // 'object'
     console.log(typeof function(){}); // 'function'
     ```

#### 48. **What are arrow functions, and how are they different from regular functions?**
   - **Answer:**
     Arrow functions are a concise syntax for writing functions in JavaScript. They have some key differences from regular functions:
     - **Syntax**: Shorter syntax using `=>`.
     - **`this` Binding**: Arrow functions do not have their own `this` context; they inherit `this` from the surrounding code.
     - **No `arguments` object**: Arrow functions do not have an `arguments` object.

     **Example:**
     ```javascript
     const add = (a, b) => a + b;
     console.log(add(2, 3)); // 5
     ```

#### 49. **What is `event.preventDefault()` in JavaScript?**
   - **Answer:**
     `event.preventDefault()` is a method that cancels the default action of an event. For example, it can prevent a form from being submitted, a link from being followed, or a checkbox from being checked.

     **Example:**
     ```javascript
     document.querySelector('form').addEventListener('submit', function(event) {
       event.preventDefault(); // Prevents the form from submitting
       console.log('Form submission prevented');
     });
     ```

#### 50. **What is `event.stopPropagation()` in JavaScript?**
   - **Answer:**
     `event.stopPropagation()` is a method that prevents an event from propagating (bubbling) up the DOM tree. This can be useful when you want to prevent a parent element's event handler from being triggered by an event on a child element.

     **Example:**
     ```javascript
     document.querySelector('.child').addEventListener('click', function(event) {
       event.stopPropagation(); // Prevents the click event from reaching parent elements
       console.log('Child clicked');
     });

     document.querySelector('.parent').addEventListener('click', function() {
       console.log('Parent clicked');
     });
     ```

These questions delve deeper into JavaScript concepts that are crucial for developers to understand, particularly in the context of web development and programming interviews.

### JavaScript Interview Questions and Answers

#### 51. **What is the `instanceof` operator in JavaScript?**
   - **Answer:**
     The `instanceof` operator checks whether an object is an instance of a specific class or constructor function. It returns `true` if the object is an instance of the specified class, and `false` otherwise.

     **Example:**
     ```javascript
     class Animal {}
     class Dog extends Animal {}

     const myDog = new Dog();

     console.log(myDog instanceof Dog);   // true
     console.log(myDog instanceof Animal); // true
     console.log(myDog instanceof Object); // true
     console.log(myDog instanceof Array);  // false
     ```

#### 52. **What are template literals in JavaScript?**
   - **Answer:**
     Template literals are a feature in ES6 that allows for easier string creation and interpolation of variables or expressions. They are defined using backticks (`` ` ``) instead of single or double quotes.

     **Features of Template Literals:**
     - **Multi-line strings**: Easily create strings that span multiple lines.
     - **String interpolation**: Embed variables or expressions within strings using `${}`.

     **Example:**
     ```javascript
     const name = 'John';
     const greeting = `Hello, ${name}! How are you today?`;

     console.log(greeting); // 'Hello, John! How are you today?'

     const multiLine = `This is a string
     that spans multiple lines.`;

     console.log(multiLine);
     // Output:
     // This is a string
     // that spans multiple lines.
     ```

#### 53. **What is the difference between `null` and `undefined` in JavaScript?**
   - **Answer:**
     - **`undefined`**: A variable that has been declared but not assigned a value will have the value `undefined`. It is the default value of uninitialized variables.
     - **`null`**: `null` is an assignment value that represents "no value" or "empty value." It is explicitly set by the developer to indicate that a variable should have no value.

     **Example:**
     ```javascript
     let a;
     console.log(a); // undefined

     let b = null;
     console.log(b); // null
     ```

#### 54. **What are IIFEs (Immediately Invoked Function Expressions) in JavaScript?**
   - **Answer:**
     An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined. The function is executed immediately, and it does not pollute the global namespace.

     **Syntax:**
     ```javascript
     (function() {
       // Function body
     })();
     ```

     **Example:**
     ```javascript
     (function() {
       let message = 'Hello, IIFE!';
       console.log(message);
     })();
     // Output: 'Hello, IIFE!'

     // The variable `message` is not accessible outside the IIFE
     // console.log(message); // ReferenceError: message is not defined
     ```

#### 55. **What is event delegation in JavaScript?**
   - **Answer:**
     Event delegation is a technique in which a single event handler is added to a parent element to manage events for all of its child elements. This is useful for efficiently managing events on elements that are dynamically added to the DOM.

     **How it works:**
     - Attach a single event listener to a parent element.
     - The event listener checks the target of the event to determine which child element was interacted with.

     **Example:**
     ```javascript
     document.querySelector('#parent').addEventListener('click', function(event) {
       if (event.target && event.target.matches('button')) {
         console.log('Button clicked:', event.target.textContent);
       }
     });

     // Dynamically added buttons will also trigger the event handler
     const newButton = document.createElement('button');
     newButton.textContent = 'New Button';
     document.querySelector('#parent').appendChild(newButton);
     ```

#### 56. **What is the difference between `call()`, `apply()`, and `bind()` in JavaScript?**
   - **Answer:**
     - **`call()`**: Invokes a function with a specified `this` context and individual arguments.
     - **`apply()`**: Similar to `call()`, but arguments are passed as an array.
     - **`bind()`**: Returns a new function with a specified `this` context and preset arguments. The new function can be called later.

     **Example:**
     ```javascript
     function greet(greeting, punctuation) {
       console.log(`${greeting}, ${this.name}${punctuation}`);
     }

     const person = { name: 'Alice' };

     greet.call(person, 'Hello', '!');  // 'Hello, Alice!'
     greet.apply(person, ['Hi', '.']);  // 'Hi, Alice.'
     const boundGreet = greet.bind(person, 'Hey');
     boundGreet('!!');  // 'Hey, Alice!!'
     ```

#### 57. **What is the `prototype` property in JavaScript?**
   - **Answer:**
     Every function in JavaScript has a `prototype` property, which is an object that is shared among all instances created by that function when used as a constructor. The `prototype` property allows you to add properties and methods that will be inherited by all instances.

     **Example:**
     ```javascript
     function Person(name) {
       this.name = name;
     }

     Person.prototype.greet = function() {
       console.log(`Hello, my name is ${this.name}`);
     };

     const john = new Person('John');
     john.greet(); // 'Hello, my name is John'
     ```

#### 58. **What are arrow functions, and what are their limitations?**
   - **Answer:**
     Arrow functions are a concise syntax for writing functions in JavaScript. They differ from traditional functions in that they do not have their own `this`, `arguments`, `super`, or `new.target`. Arrow functions are best suited for non-method functions and callbacks.

     **Limitations:**
     - **No `this` binding**: `this` is lexically bound to the context in which the arrow function is defined.
     - **Cannot be used as constructors**: Arrow functions do not have a `new` target and cannot be used with the `new` keyword.
     - **No `arguments` object**: Arrow functions do not have an `arguments` object; use rest parameters instead.

     **Example:**
     ```javascript
     const obj = {
       name: 'Alice',
       regularFunc: function() {
         console.log(this.name);
       },
       arrowFunc: () => {
         console.log(this.name); // `this` refers to the global context, not `obj`
       }
     };

     obj.regularFunc(); // 'Alice'
     obj.arrowFunc();   // undefined (or window.name in browsers)
     ```

#### 59. **What is `strict mode` in JavaScript, and why is it useful?**
   - **Answer:**
     `strict mode` is a feature in JavaScript that enables a stricter parsing and error handling of your code. It catches common coding mistakes and throws errors, helps avoid unsafe actions like global variable creation, and disables some features that are confusing or poorly thought out.

     **How to enable strict mode:**
     - You can enable strict mode for an entire script or for individual functions by adding `"use strict";` at the beginning of the script or function.

     **Example:**
     ```javascript
     "use strict";

     x = 10; // Throws an error: x is not defined

     function myFunction() {
       "use strict";
       // Function-level strict mode
       y = 20; // Throws an error: y is not defined
     }
     ```

#### 60. **What is destructuring in JavaScript, and how does it work?**
   - **Answer:**
     Destructuring is a feature in JavaScript that allows you to unpack values from arrays or properties from objects into distinct variables.

     **Array Destructuring:**
     ```javascript
     const numbers = [1, 2, 3];
     const [first, second, third] = numbers;
     console.log(first, second, third); // 1, 2, 3
     ```

     **Object Destructuring:**
     ```javascript
     const person = { name: 'Alice', age: 30 };
     const { name, age } = person;
     console.log(name, age); // 'Alice', 30
     ```

     **Default Values:**
     ```javascript
     const { name = 'Unknown', city = 'Unknown' } = { name: 'Alice' };
     console.log(name, city); // 'Alice', 'Unknown'
     ```

These questions cover a range of intermediate to advanced JavaScript concepts that are crucial for understanding the language deeply and performing well in technical interviews.


### JavaScript Interview Questions and Answers

#### 61. **What is a closure in JavaScript?**
   - **Answer:**
     A closure is a function that has access to its own scope, the scope of the outer function, and the global scope. Closures are created whenever a function is created within another function, allowing the inner function to access the variables of the outer function even after the outer function has returned.

     **Example:**
     ```javascript
     function outerFunction() {
       let outerVariable = 'I am outside!';

       function innerFunction() {
         console.log(outerVariable);
       }

       return innerFunction;
     }

     const myClosure = outerFunction();
     myClosure(); // 'I am outside!'
     ```

#### 62. **What is the difference between `map()`, `filter()`, and `reduce()` in JavaScript?**
   - **Answer:**
     - **`map()`**: Creates a new array by applying a function to each element of the original array.
     - **`filter()`**: Creates a new array with all elements that pass a test implemented by the provided function.
     - **`reduce()`**: Reduces an array to a single value by applying a function to each element, carrying over the result to the next iteration.

     **Examples:**
     ```javascript
     const numbers = [1, 2, 3, 4, 5];

     const doubled = numbers.map(num => num * 2);
     console.log(doubled); // [2, 4, 6, 8, 10]

     const even = numbers.filter(num => num % 2 === 0);
     console.log(even); // [2, 4]

     const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
     console.log(sum); // 15
     ```

#### 63. **What is the purpose of the `await` keyword in JavaScript?**
   - **Answer:**
     The `await` keyword is used in conjunction with `async` functions to pause the execution of the function until a `Promise` is resolved or rejected. It simplifies working with asynchronous code by allowing you to write code that looks synchronous.

     **Example:**
     ```javascript
     async function fetchData() {
       try {
         const response = await fetch('https://api.example.com/data');
         const data = await response.json();
         console.log(data);
       } catch (error) {
         console.error('Error fetching data:', error);
       }
     }

     fetchData();
     ```

#### 64. **What are modules in JavaScript?**
   - **Answer:**
     Modules in JavaScript are reusable pieces of code that are encapsulated in their own scope, allowing you to import and export functionality between files. This helps in organizing and maintaining code, especially in large projects.

     **Example using ES6 Modules:**
     ```javascript
     // math.js
     export function add(a, b) {
       return a + b;
     }

     export function subtract(a, b) {
       return a - b;
     }

     // main.js
     import { add, subtract } from './math.js';

     console.log(add(2, 3)); // 5
     console.log(subtract(5, 3)); // 2
     ```

#### 65. **What is the `typeof` operator in JavaScript?**
   - **Answer:**
     The `typeof` operator returns a string indicating the type of a given variable or expression. It is commonly used to determine the type of a variable before performing operations on it.

     **Example:**
     ```javascript
     console.log(typeof 42);           // 'number'
     console.log(typeof 'Hello');      // 'string'
     console.log(typeof true);         // 'boolean'
     console.log(typeof undefined);    // 'undefined'
     console.log(typeof null);         // 'object' (this is a known quirk)
     console.log(typeof {});           // 'object'
     console.log(typeof function() {}); // 'function'
     ```

#### 66. **What is the event loop in JavaScript?**
   - **Answer:**
     The event loop is a mechanism in JavaScript that handles asynchronous operations by continuously checking the message queue and executing any queued tasks (e.g., callback functions) when the call stack is empty. It allows JavaScript to perform non-blocking I/O operations despite being single-threaded.

     **Example:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Timeout');
     }, 0);

     console.log('End');

     // Output:
     // Start
     // End
     // Timeout
     ```

#### 67. **What are promises in JavaScript, and how do they work?**
   - **Answer:**
     Promises are objects representing the eventual completion (or failure) of an asynchronous operation and its resulting value. They have three states: `pending`, `fulfilled`, and `rejected`.

     **Example:**
     ```javascript
     const myPromise = new Promise((resolve, reject) => {
       let success = true;
       if (success) {
         resolve('Operation succeeded');
       } else {
         reject('Operation failed');
       }
     });

     myPromise
       .then(result => {
         console.log(result); // 'Operation succeeded'
       })
       .catch(error => {
         console.error(error);
       });
     ```

#### 68. **What is the `this` keyword in JavaScript, and how is it determined?**
   - **Answer:**
     The `this` keyword refers to the context in which a function is executed. The value of `this` is determined by how a function is called:
     - **Global Context**: In the global context, `this` refers to the global object (e.g., `window` in browsers).
     - **Object Method**: When a function is called as a method of an object, `this` refers to the object.
     - **Constructor Function**: In a constructor function, `this` refers to the newly created object.
     - **Arrow Functions**: `this` in arrow functions is lexically bound and refers to the context in which the arrow function was defined.

     **Example:**
     ```javascript
     const obj = {
       name: 'Alice',
       greet: function() {
         console.log(this.name);
       }
     };

     obj.greet(); // 'Alice'

     const greet = obj.greet;
     greet(); // undefined (in strict mode) or 'window.name' (in non-strict mode)

     const arrowGreet = () => {
       console.log(this.name);
     };

     arrowGreet(); // undefined (or 'window.name' if in a browser global context)
     ```

#### 69. **What is hoisting in JavaScript?**
   - **Answer:**
     Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that variables can be used before they are declared, but they are initialized with `undefined`.

     **Example:**
     ```javascript
     console.log(a); // undefined
     var a = 5;

     console.log(b); // ReferenceError: Cannot access 'b' before initialization
     let b = 10;

     // Function Hoisting
     hoistedFunction(); // 'This function is hoisted!'

     function hoistedFunction() {
       console.log('This function is hoisted!');
     }
     ```

#### 70. **What are higher-order functions in JavaScript?**
   - **Answer:**
     Higher-order functions are functions that can take other functions as arguments, return functions, or both. They are a key concept in functional programming.

     **Example:**
     ```javascript
     function higherOrderFunction(callback) {
       const message = 'Hello, World!';
       callback(message);
     }

     function printMessage(msg) {
       console.log(msg);
     }

     higherOrderFunction(printMessage); // 'Hello, World!'

     // Returning a function
     function multiplier(factor) {
       return function(number) {
         return number * factor;
       };
     }

     const double = multiplier(2);
     console.log(double(5)); // 10
     ```

These questions continue to cover important concepts in JavaScript that are essential for both interviews and real-world development.

### JavaScript Interview Questions and Answers

#### 71. **What is the difference between `call()`, `apply()`, and `bind()` in JavaScript?**
   - **Answer:**
     - **`call()`**: Invokes a function with a given `this` value and arguments provided individually.
     - **`apply()`**: Similar to `call()`, but arguments are provided as an array.
     - **`bind()`**: Returns a new function with a given `this` value and optionally some arguments pre-filled, without immediately invoking it.

     **Example:**
     ```javascript
     function greet(greeting, punctuation) {
       console.log(greeting + ', ' + this.name + punctuation);
     }

     const person = { name: 'John' };

     greet.call(person, 'Hello', '!');   // 'Hello, John!'
     greet.apply(person, ['Hi', '.']);   // 'Hi, John.'
     const greetJohn = greet.bind(person, 'Hey');
     greetJohn('?');                     // 'Hey, John?'
     ```

#### 72. **What are arrow functions, and how do they differ from traditional functions?**
   - **Answer:**
     Arrow functions are a more concise syntax for writing functions in JavaScript. They differ from traditional functions in several ways:
     - They do not have their own `this` context, meaning `this` is lexically inherited from the surrounding scope.
     - They do not have their own `arguments` object.
     - They cannot be used as constructors (`new` will throw an error).

     **Example:**
     ```javascript
     const add = (a, b) => a + b;
     console.log(add(2, 3)); // 5

     const person = {
       name: 'Alice',
       sayName: function() {
         setTimeout(() => {
           console.log(this.name); // 'Alice' - because 'this' is inherited
         }, 100);
       }
     };

     person.sayName();
     ```

#### 73. **What is a promise chain in JavaScript?**
   - **Answer:**
     A promise chain is a series of `.then()` calls on a promise, where each `.then()` returns a new promise. It allows you to handle a sequence of asynchronous operations in a clear and readable manner.

     **Example:**
     ```javascript
     new Promise((resolve, reject) => {
       resolve(1);
     })
     .then(result => {
       console.log(result); // 1
       return result * 2;
     })
     .then(result => {
       console.log(result); // 2
       return result * 3;
     })
     .then(result => {
       console.log(result); // 6
     })
     .catch(error => {
       console.error(error);
     });
     ```

#### 74. **What is the purpose of `Symbol` in JavaScript?**
   - **Answer:**
     `Symbol` is a primitive data type introduced in ES6 that represents a unique and immutable identifier. Symbols are often used to add unique keys to objects without risk of collision with other keys, ensuring that properties do not accidentally overwrite each other.

     **Example:**
     ```javascript
     const sym1 = Symbol('description');
     const sym2 = Symbol('description');

     console.log(sym1 === sym2); // false

     const obj = {
       [sym1]: 'value1',
       [sym2]: 'value2'
     };

     console.log(obj[sym1]); // 'value1'
     console.log(obj[sym2]); // 'value2'
     ```

#### 75. **What is event delegation in JavaScript?**
   - **Answer:**
     Event delegation is a technique where a single event listener is added to a parent element to manage events for all of its child elements. This is particularly useful for managing events on dynamically generated elements.

     **Example:**
     ```javascript
     document.getElementById('parent').addEventListener('click', function(event) {
       if (event.target && event.target.matches('button.someClass')) {
         console.log('Button clicked:', event.target.textContent);
       }
     });

     // Now, any button with the class 'someClass' inside the 'parent' element will trigger the event.
     ```

#### 76. **What are rest parameters in JavaScript?**
   - **Answer:**
     Rest parameters allow you to represent an indefinite number of arguments as an array. They are denoted by three dots (`...`) followed by the parameter name.

     **Example:**
     ```javascript
     function sum(...numbers) {
       return numbers.reduce((acc, curr) => acc + curr, 0);
     }

     console.log(sum(1, 2, 3)); // 6
     console.log(sum(4, 5, 6, 7)); // 22
     ```

#### 77. **What is the difference between synchronous and asynchronous code in JavaScript?**
   - **Answer:**
     - **Synchronous code**: Executes sequentially, one operation at a time, blocking the execution of further code until the current operation is completed.
     - **Asynchronous code**: Allows other code to run while waiting for operations like network requests, timers, or file I/O to complete, typically handled via callbacks, promises, or `async/await`.

     **Example:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Async operation');
     }, 1000);

     console.log('End');

     // Output:
     // Start
     // End
     // Async operation (after 1 second)
     ```

#### 78. **What is the difference between `let`, `const`, and `var`?**
   - **Answer:**
     - **`var`**: Function-scoped, can be re-declared, and hoisted with `undefined` initialization.
     - **`let`**: Block-scoped, cannot be re-declared in the same scope, and hoisted but not initialized.
     - **`const`**: Block-scoped, must be initialized at declaration, and cannot be reassigned.

     **Example:**
     ```javascript
     function demoVar() {
       console.log(x); // undefined (due to hoisting)
       var x = 5;
       console.log(x); // 5
     }

     function demoLetConst() {
       let y = 10;
       const z = 20;

       y = 15; // Allowed
       z = 25; // Error: Assignment to constant variable
     }
     ```

#### 79. **What are default parameters in JavaScript?**
   - **Answer:**
     Default parameters allow you to set default values for function parameters if no argument is provided. They make your code more concise and eliminate the need for manual checks for `undefined`.

     **Example:**
     ```javascript
     function greet(name = 'Guest') {
       console.log(`Hello, ${name}!`);
     }

     greet(); // 'Hello, Guest!'
     greet('Alice'); // 'Hello, Alice!'
     ```

#### 80. **What is the `new` keyword in JavaScript?**
   - **Answer:**
     The `new` keyword is used to create an instance of an object that has a constructor function. When `new` is used, it:
     1. Creates a new empty object.
     2. Sets the `this` value to the new object.
     3. Links the object to a prototype.
     4. Returns the new object from the constructor function.

     **Example:**
     ```javascript
     function Person(name, age) {
       this.name = name;
       this.age = age;
     }

     const person1 = new Person('John', 30);
     console.log(person1.name); // 'John'
     console.log(person1.age);  // 30
     ```

These questions continue to explore deeper aspects of JavaScript, covering essential concepts that are vital for understanding how the language operates in various contexts.

### JavaScript Interview Questions and Answers

#### 81. **What is the `instanceof` operator in JavaScript?**
   - **Answer:**
     The `instanceof` operator checks if an object is an instance of a particular constructor or class. It returns `true` if the object’s prototype chain includes the prototype property of the constructor, otherwise it returns `false`.

     **Example:**
     ```javascript
     function Person(name) {
       this.name = name;
     }

     const person1 = new Person('Alice');

     console.log(person1 instanceof Person); // true
     console.log(person1 instanceof Object); // true
     console.log(person1 instanceof Array);  // false
     ```

#### 82. **What is the difference between `==` and `===` in JavaScript?**
   - **Answer:**
     - **`==` (Loose equality):** Compares two values for equality after converting both values to a common type. It performs type coercion if necessary.
     - **`===` (Strict equality):** Compares two values for equality without converting them. The values must be of the same type to be considered equal.

     **Example:**
     ```javascript
     console.log(5 == '5');  // true (because '5' is converted to 5)
     console.log(5 === '5'); // false (because types are different)
     ```

#### 83. **What is hoisting in JavaScript?**
   - **Answer:**
     Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that variables and functions can be used before they are declared in the code.

     **Example:**
     ```javascript
     console.log(a); // undefined (hoisted with no initial value)
     var a = 5;

     greet(); // 'Hello!' (function declaration is hoisted)

     function greet() {
       console.log('Hello!');
     }
     ```

#### 84. **What are Immediately Invoked Function Expressions (IIFE)?**
   - **Answer:**
     An IIFE is a function that is executed immediately after it is defined. It is often used to create a private scope to avoid polluting the global namespace.

     **Example:**
     ```javascript
     (function() {
       var message = 'Hello, World!';
       console.log(message);
     })();

     // The 'message' variable is not accessible outside the IIFE.
     ```

#### 85. **What is the `arguments` object in JavaScript?**
   - **Answer:**
     The `arguments` object is an array-like object available within functions that contains the values of the arguments passed to that function. It can be used to access arguments that were passed to the function but not explicitly defined as parameters.

     **Example:**
     ```javascript
     function sum() {
       let total = 0;
       for (let i = 0; i < arguments.length; i++) {
         total += arguments[i];
       }
       return total;
     }

     console.log(sum(1, 2, 3, 4)); // 10
     ```

#### 86. **What is the difference between `null` and `undefined` in JavaScript?**
   - **Answer:**
     - **`undefined`:** A variable that has been declared but not assigned a value is `undefined`.
     - **`null`:** An assignment value representing the intentional absence of any object value.

     **Example:**
     ```javascript
     let a;
     console.log(a); // undefined

     let b = null;
     console.log(b); // null
     ```

#### 87. **What is event bubbling and event capturing in JavaScript?**
   - **Answer:**
     - **Event bubbling**: When an event is triggered on a specific element, it first runs the handlers on that element, and then on its parent, and then on its grandparent, and so on, up the DOM tree.
     - **Event capturing**: The event starts from the outermost element and goes down to the target element.

     **Example:**
     ```javascript
     document.querySelector("#child").addEventListener("click", function() {
       console.log("Child clicked");
     });

     document.querySelector("#parent").addEventListener("click", function() {
       console.log("Parent clicked");
     });

     // If you click on the child element, "Child clicked" will be logged first, then "Parent clicked" (bubbling).
     ```

#### 88. **What are the different ways to iterate over an array in JavaScript?**
   - **Answer:**
     You can iterate over an array in JavaScript using various methods:
     - **`for` loop**: Traditional loop with index.
     - **`forEach`**: Array method that executes a provided function once for each array element.
     - **`for...of`**: ES6 loop that iterates over iterable objects.
     - **`map()`**: Array method that creates a new array populated with the results of calling a provided function on every element in the calling array.
     - **`reduce()`**: Array method that executes a reducer function on each element, resulting in a single output value.

     **Example:**
     ```javascript
     const arr = [1, 2, 3, 4];

     // Using a 'for' loop
     for (let i = 0; i < arr.length; i++) {
       console.log(arr[i]);
     }

     // Using 'forEach'
     arr.forEach(item => console.log(item));

     // Using 'for...of'
     for (const item of arr) {
       console.log(item);
     }

     // Using 'map'
     const doubled = arr.map(item => item * 2);
     console.log(doubled); // [2, 4, 6, 8]

     // Using 'reduce'
     const sum = arr.reduce((acc, curr) => acc + curr, 0);
     console.log(sum); // 10
     ```

#### 89. **What is a closure in JavaScript?**
   - **Answer:**
     A closure is a feature in JavaScript where an inner function has access to the outer (enclosing) function's variables even after the outer function has returned. Closures are created every time a function is created, at function creation time.

     **Example:**
     ```javascript
     function outerFunction() {
       let outerVariable = 'I am outside!';

       function innerFunction() {
         console.log(outerVariable);
       }

       return innerFunction;
     }

     const closure = outerFunction();
     closure(); // 'I am outside!'
     ```

#### 90. **What are template literals in JavaScript?**
   - **Answer:**
     Template literals are string literals that allow embedded expressions. They are enclosed by backticks (\`\`) and can contain placeholders represented by `${expression}`. Template literals can span multiple lines and include variables or expressions directly in the string.

     **Example:**
     ```javascript
     const name = 'John';
     const age = 30;

     const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
     console.log(greeting); // 'Hello, my name is John and I am 30 years old.'

     const multiline = `This is a 
     multiline string.`;
     console.log(multiline);
     ```

These questions provide deeper insights into JavaScript, focusing on fundamental concepts, language features, and common patterns used in modern JavaScript development.

### JavaScript Interview Questions and Answers

#### 91. **What is the `call()` method in JavaScript? How is it different from `apply()`?**
   - **Answer:**
     The `call()` method is used to call a function with a given `this` value and arguments provided individually. It allows you to invoke a function and specify what `this` should refer to.

     The `apply()` method is similar to `call()`, but it takes arguments as an array (or array-like object) instead of listing them individually.

     **Example:**
     ```javascript
     function greet(greeting, punctuation) {
       console.log(greeting + ', ' + this.name + punctuation);
     }

     const person = { name: 'Alice' };

     greet.call(person, 'Hello', '!');  // 'Hello, Alice!'
     greet.apply(person, ['Hi', '.']);  // 'Hi, Alice.'
     ```

#### 92. **What is the difference between `let`, `const`, and `var`?**
   - **Answer:**
     - **`var`:** Function-scoped or globally-scoped, can be re-declared and updated. Variables declared with `var` are hoisted to the top of their scope and initialized with `undefined`.
     - **`let`:** Block-scoped, cannot be re-declared within the same scope, but can be updated. Variables declared with `let` are hoisted but not initialized.
     - **`const`:** Block-scoped, cannot be re-declared or updated. A `const` variable must be initialized at the time of declaration.

     **Example:**
     ```javascript
     var a = 1;
     let b = 2;
     const c = 3;

     function example() {
       var a = 10;
       let b = 20;
       const c = 30;
       console.log(a, b, c); // 10, 20, 30
     }

     example();
     console.log(a, b, c); // 1, 2, 3
     ```

#### 93. **What is the purpose of `Object.freeze()` in JavaScript?**
   - **Answer:**
     `Object.freeze()` is used to freeze an object, preventing new properties from being added to it, existing properties from being removed, and any existing properties from being changed. In effect, the object becomes immutable.

     **Example:**
     ```javascript
     const obj = {
       name: 'Alice',
       age: 25
     };

     Object.freeze(obj);

     obj.age = 30; // This will not change the age
     delete obj.name; // This will not delete the name property

     console.log(obj); // { name: 'Alice', age: 25 }
     ```

#### 94. **What is the difference between `Object.seal()` and `Object.freeze()`?**
   - **Answer:**
     - **`Object.freeze()`**: Makes an object immutable. Properties cannot be added, deleted, or modified.
     - **`Object.seal()`**: Prevents new properties from being added and existing properties from being deleted. However, it allows existing properties to be modified (as long as they are not non-writable).

     **Example:**
     ```javascript
     const obj = { name: 'Alice', age: 25 };

     Object.seal(obj);
     obj.age = 30; // Allowed
     delete obj.name; // Not allowed

     console.log(obj); // { name: 'Alice', age: 30 }

     Object.freeze(obj);
     obj.age = 35; // Not allowed
     console.log(obj); // { name: 'Alice', age: 30 }
     ```

#### 95. **What is a generator function in JavaScript?**
   - **Answer:**
     A generator function is a special type of function that can be paused and resumed. It is defined using the `function*` syntax and returns an iterator object. The `yield` keyword is used to pause the function and return a value.

     **Example:**
     ```javascript
     function* generatorFunction() {
       yield 'First output';
       yield 'Second output';
       return 'Done';
     }

     const generator = generatorFunction();

     console.log(generator.next()); // { value: 'First output', done: false }
     console.log(generator.next()); // { value: 'Second output', done: false }
     console.log(generator.next()); // { value: 'Done', done: true }
     ```

#### 96. **What is the purpose of the `super` keyword in JavaScript?**
   - **Answer:**
     The `super` keyword is used to call the constructor of the parent class and to access parent class methods. It is used in classes that inherit from other classes using the `extends` keyword.

     **Example:**
     ```javascript
     class Parent {
       constructor(name) {
         this.name = name;
       }

       greet() {
         console.log(`Hello, ${this.name}`);
       }
     }

     class Child extends Parent {
       constructor(name, age) {
         super(name);
         this.age = age;
       }

       greet() {
         super.greet();
         console.log(`You are ${this.age} years old`);
       }
     }

     const child = new Child('Alice', 10);
     child.greet();
     // Output:
     // Hello, Alice
     // You are 10 years old
     ```

#### 97. **What is the purpose of the `new` keyword in JavaScript?**
   - **Answer:**
     The `new` keyword is used to create an instance of an object that has a constructor function. It performs the following tasks:
     1. Creates a new empty object.
     2. Sets the prototype of the new object to the constructor’s prototype.
     3. Binds `this` to the new object inside the constructor function.
     4. Returns the new object unless the constructor function returns a non-primitive value.

     **Example:**
     ```javascript
     function Person(name) {
       this.name = name;
     }

     const person1 = new Person('Alice');
     console.log(person1.name); // 'Alice'
     ```

#### 98. **What are default parameters in JavaScript?**
   - **Answer:**
     Default parameters allow you to initialize a function parameter with a default value if no value is provided or if `undefined` is passed.

     **Example:**
     ```javascript
     function greet(name = 'Guest') {
       console.log(`Hello, ${name}`);
     }

     greet('Alice'); // 'Hello, Alice'
     greet();        // 'Hello, Guest'
     ```

#### 99. **What is destructuring assignment in JavaScript?**
   - **Answer:**
     Destructuring assignment is a syntax that allows you to unpack values from arrays or properties from objects into distinct variables.

     **Example:**
     ```javascript
     // Array destructuring
     const [a, b] = [1, 2];
     console.log(a); // 1
     console.log(b); // 2

     // Object destructuring
     const person = { name: 'Alice', age: 25 };
     const { name, age } = person;
     console.log(name); // 'Alice'
     console.log(age);  // 25
     ```

#### 100. **What is a promise in JavaScript?**
   - **Answer:**
     A promise is an object representing the eventual completion or failure of an asynchronous operation. It allows you to write asynchronous code in a more manageable way, avoiding callback hell.

     **Example:**
     ```javascript
     const promise = new Promise((resolve, reject) => {
       const success = true;

       if (success) {
         resolve('Operation succeeded');
       } else {
         reject('Operation failed');
       }
     });

     promise
       .then(result => console.log(result)) // 'Operation succeeded'
       .catch(error => console.error(error));
     ```

These questions delve into advanced JavaScript topics and help solidify an understanding of key concepts and features of the language.


### JavaScript Interview Questions and Answers

#### 101. **What are IIFEs (Immediately Invoked Function Expressions) in JavaScript?**
   - **Answer:**
     An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined. It’s a design pattern that is often used to create a local scope for variables and avoid polluting the global namespace.

     **Example:**
     ```javascript
     (function() {
       console.log('This is an IIFE');
     })();
     ```

#### 102. **What is the difference between `==` and `===` in JavaScript?**
   - **Answer:**
     - **`==`:** Checks for equality after converting both values to a common type (type coercion).
     - **`===`:** Checks for equality without type conversion (strict equality).

     **Example:**
     ```javascript
     console.log(1 == '1');  // true
     console.log(1 === '1'); // false
     ```

#### 103. **What is a closure in JavaScript?**
   - **Answer:**
     A closure is a function that remembers the environment in which it was created. It has access to variables from its outer function even after the outer function has finished executing.

     **Example:**
     ```javascript
     function outerFunction() {
       let outerVariable = 'I am from outer function';

       function innerFunction() {
         console.log(outerVariable);
       }

       return innerFunction;
     }

     const closure = outerFunction();
     closure(); // 'I am from outer function'
     ```

#### 104. **What is event delegation in JavaScript?**
   - **Answer:**
     Event delegation is a technique in JavaScript where a single event listener is added to a parent element to manage events for all its children. This is particularly useful for handling events on dynamically added elements.

     **Example:**
     ```javascript
     document.querySelector('#parent').addEventListener('click', function(event) {
       if (event.target && event.target.nodeName == 'BUTTON') {
         console.log('Button clicked:', event.target.textContent);
       }
     });
     ```

#### 105. **What are arrow functions in JavaScript?**
   - **Answer:**
     Arrow functions are a shorthand syntax for writing functions in JavaScript. They do not have their own `this`, `arguments`, `super`, or `new.target` bindings, making them ideal for non-method functions.

     **Example:**
     ```javascript
     const add = (a, b) => a + b;
     console.log(add(2, 3)); // 5
     ```

#### 106. **What is the `fetch` API in JavaScript?**
   - **Answer:**
     The `fetch` API provides a modern way to make network requests in JavaScript. It returns a Promise that resolves to the Response object representing the response to the request.

     **Example:**
     ```javascript
     fetch('https://api.example.com/data')
       .then(response => response.json())
       .then(data => console.log(data))
       .catch(error => console.error('Error:', error));
     ```

#### 107. **What is the purpose of the `async` and `await` keywords in JavaScript?**
   - **Answer:**
     The `async` keyword is used to define an asynchronous function, which returns a Promise. The `await` keyword is used to pause the execution of an `async` function until the Promise is resolved or rejected.

     **Example:**
     ```javascript
     async function fetchData() {
       try {
         const response = await fetch('https://api.example.com/data');
         const data = await response.json();
         console.log(data);
       } catch (error) {
         console.error('Error:', error);
       }
     }

     fetchData();
     ```

#### 108. **What is the difference between `null` and `undefined` in JavaScript?**
   - **Answer:**
     - **`undefined`:** Indicates that a variable has been declared but has not yet been assigned a value.
     - **`null`:** Represents the intentional absence of any object value. It’s an assignment value.

     **Example:**
     ```javascript
     let a;
     console.log(a); // undefined

     let b = null;
     console.log(b); // null
     ```

#### 109. **What are template literals in JavaScript?**
   - **Answer:**
     Template literals are a way to include variables and expressions inside a string without concatenation. They use backticks (`` ` ``) and support multi-line strings and string interpolation with `${}`.

     **Example:**
     ```javascript
     const name = 'Alice';
     const greeting = `Hello, ${name}!`;
     console.log(greeting); // 'Hello, Alice!'
     ```

#### 110. **What is the difference between synchronous and asynchronous code in JavaScript?**
   - **Answer:**
     - **Synchronous code:** Executes sequentially, blocking the execution of other code until it finishes.
     - **Asynchronous code:** Executes without blocking, allowing other code to run while it’s waiting for an operation (like an API call) to complete.

     **Example:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Async Operation');
     }, 1000);

     console.log('End');

     // Output:
     // Start
     // End
     // Async Operation (after 1 second)
     ```

These questions continue to explore advanced topics in JavaScript, providing insights into the language’s features and capabilities.

### JavaScript Interview Questions and Answers

#### 111. **What is the `typeof` operator in JavaScript?**
   - **Answer:**
     The `typeof` operator returns a string indicating the type of the operand. It can be used to check whether a variable is a string, number, object, function, etc.

     **Example:**
     ```javascript
     console.log(typeof 'Hello'); // 'string'
     console.log(typeof 42);      // 'number'
     console.log(typeof true);    // 'boolean'
     console.log(typeof {});      // 'object'
     console.log(typeof undefined); // 'undefined'
     console.log(typeof null);    // 'object' (this is a quirk in JavaScript)
     ```

#### 112. **What is the event loop in JavaScript?**
   - **Answer:**
     The event loop is a mechanism that allows JavaScript to perform non-blocking operations, even though JavaScript is single-threaded. It continuously checks the call stack and the message queue, executing tasks in order.

     **Example:**
     ```javascript
     console.log('Start');

     setTimeout(() => {
       console.log('Timeout callback');
     }, 0);

     console.log('End');

     // Output:
     // Start
     // End
     // Timeout callback
     ```

#### 113. **What is hoisting in JavaScript?**
   - **Answer:**
     Hoisting is JavaScript's behavior of moving declarations (but not initializations) to the top of their containing scope during the compilation phase. This applies to both `var` variables and function declarations.

     **Example:**
     ```javascript
     console.log(hoistedVar); // undefined
     var hoistedVar = 'This is hoisted';

     hoistedFunction(); // 'This function is hoisted'

     function hoistedFunction() {
       console.log('This function is hoisted');
     }
     ```

#### 114. **What is a `Map` in JavaScript, and how is it different from an object?**
   - **Answer:**
     A `Map` is a collection of key-value pairs where keys can be of any type. It preserves the order of insertion and has methods like `set`, `get`, `delete`, and `has`.

     **Differences from an Object:**
     - A `Map` allows any type of key (not just strings or symbols).
     - A `Map` preserves the order of its elements.
     - A `Map` has a size property directly available (`map.size`), whereas an object's size must be calculated manually.

     **Example:**
     ```javascript
     const map = new Map();
     map.set('name', 'Alice');
     map.set(42, 'Age');

     console.log(map.get('name')); // 'Alice'
     console.log(map.get(42));     // 'Age'
     ```

#### 115. **What is the `Set` object in JavaScript?**
   - **Answer:**
     A `Set` is a collection of unique values, meaning it only stores values that are not repeated. Sets can hold any type of values, whether primitive or object references.

     **Example:**
     ```javascript
     const set = new Set([1, 2, 3, 3, 4]);
     console.log(set); // Set { 1, 2, 3, 4 }

     set.add(5);
     set.add(3); // 3 is already in the set, so it won't be added again

     console.log(set.has(5)); // true
     console.log(set.size);   // 5
     ```

#### 116. **What is a `WeakMap` in JavaScript?**
   - **Answer:**
     A `WeakMap` is a collection of key-value pairs where the keys are objects and the values can be arbitrary values. A `WeakMap` holds "weak" references to the keys, meaning that if there are no other references to the key object, the entry in the `WeakMap` can be garbage-collected.

     **Example:**
     ```javascript
     let obj = { name: 'Alice' };
     const weakMap = new WeakMap();

     weakMap.set(obj, 'some value');

     console.log(weakMap.get(obj)); // 'some value'

     obj = null; // Now the object can be garbage collected
     ```

#### 117. **What are higher-order functions in JavaScript?**
   - **Answer:**
     A higher-order function is a function that either takes another function as an argument or returns a function as a result. Higher-order functions allow for more abstract and reusable code.

     **Example:**
     ```javascript
     function greet(name) {
       return function(message) {
         console.log(`${message}, ${name}`);
       };
     }

     const greetAlice = greet('Alice');
     greetAlice('Hello'); // 'Hello, Alice'
     greetAlice('Goodbye'); // 'Goodbye, Alice'
     ```

#### 118. **What is the `Proxy` object in JavaScript?**
   - **Answer:**
     A `Proxy` object is used to define custom behavior for fundamental operations (e.g., property lookup, assignment, enumeration, function invocation). A `Proxy` is created with two parameters: the target object and a handler object that defines the custom behavior.

     **Example:**
     ```javascript
     const target = {
       message: 'Hello, World!'
     };

     const handler = {
       get: function(target, prop, receiver) {
         if (prop === 'message') {
           return target[prop].toUpperCase();
         }
         return target[prop];
       }
     };

     const proxy = new Proxy(target, handler);
     console.log(proxy.message); // 'HELLO, WORLD!'
     ```

#### 119. **What is the `Reflect` object in JavaScript?**
   - **Answer:**
     The `Reflect` object provides methods for interceptable JavaScript operations. These methods are the same as those provided by the proxy handlers, and they allow you to perform default operations in a straightforward way.

     **Example:**
     ```javascript
     const obj = { name: 'Alice' };

     console.log(Reflect.has(obj, 'name')); // true
     Reflect.set(obj, 'age', 25);
     console.log(obj.age); // 25
     ```

#### 120. **What is the purpose of `async` and `await` in JavaScript?**
   - **Answer:**
     The `async` keyword is used to declare an asynchronous function, and the `await` keyword is used to pause the execution of an `async` function until a Promise is resolved or rejected. This allows for easier handling of asynchronous code without chaining `.then()` methods.

     **Example:**
     ```javascript
     async function fetchData() {
       try {
         const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
         const data = await response.json();
         console.log(data);
       } catch (error) {
         console.error('Error:', error);
       }
     }

     fetchData();
     ```

These questions provide further insight into JavaScript’s advanced features, helping to solidify a deep understanding of the language.

### JavaScript Interview Questions and Answers

#### 121. **What is the difference between `Object.seal()` and `Object.freeze()` in JavaScript?**
   - **Answer:**
     - **`Object.seal()`:** Prevents new properties from being added to an object and marks all existing properties as non-configurable. However, values of existing properties can still be changed.
     - **`Object.freeze()`:** Freezes an object, preventing new properties from being added, existing properties from being removed, and any changes to existing property values. The object becomes immutable.

     **Example:**
     ```javascript
     const obj = { name: 'Alice' };

     Object.seal(obj);
     obj.age = 25;       // Cannot add new property
     obj.name = 'Bob';   // Can modify existing property
     console.log(obj);   // { name: 'Bob' }

     Object.freeze(obj);
     obj.name = 'Charlie'; // Cannot modify property
     console.log(obj);     // { name: 'Bob' }
     ```

#### 122. **What is the purpose of the `reduce()` method in JavaScript?**
   - **Answer:**
     The `reduce()` method executes a reducer function on each element of an array, resulting in a single output value. It’s commonly used to sum the values of an array, but can also be used for more complex operations.

     **Example:**
     ```javascript
     const numbers = [1, 2, 3, 4, 5];
     const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
     console.log(sum); // 15
     ```

#### 123. **What are JavaScript Promises and how do they work?**
   - **Answer:**
     A Promise is an object representing the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises have three states: `pending`, `fulfilled`, and `rejected`.

     **Example:**
     ```javascript
     const promise = new Promise((resolve, reject) => {
       const success = true;
       if (success) {
         resolve('Operation was successful');
       } else {
         reject('Operation failed');
       }
     });

     promise
       .then(result => console.log(result))   // 'Operation was successful'
       .catch(error => console.log(error));   // This won't run
     ```

#### 124. **What is the `spread` operator in JavaScript?**
   - **Answer:**
     The spread operator (`...`) allows an iterable (like an array or string) to be expanded in places where zero or more arguments or elements are expected. It can also be used to create shallow copies of arrays or objects.

     **Example:**
     ```javascript
     const arr1 = [1, 2, 3];
     const arr2 = [...arr1, 4, 5, 6];
     console.log(arr2); // [1, 2, 3, 4, 5, 6]

     const obj1 = { name: 'Alice', age: 25 };
     const obj2 = { ...obj1, location: 'NYC' };
     console.log(obj2); // { name: 'Alice', age: 25, location: 'NYC' }
     ```

#### 125. **What is the `rest` parameter in JavaScript?**
   - **Answer:**
     The rest parameter (`...`) allows a function to accept an indefinite number of arguments as an array. It’s useful for handling function arguments that are not predetermined.

     **Example:**
     ```javascript
     function sum(...numbers) {
       return numbers.reduce((acc, num) => acc + num, 0);
     }

     console.log(sum(1, 2, 3, 4)); // 10
     ```

#### 126. **What is the purpose of `Object.assign()` in JavaScript?**
   - **Answer:**
     `Object.assign()` is used to copy the values of all enumerable own properties from one or more source objects to a target object. It returns the target object.

     **Example:**
     ```javascript
     const target = { a: 1, b: 2 };
     const source = { b: 4, c: 5 };

     const result = Object.assign(target, source);
     console.log(result); // { a: 1, b: 4, c: 5 }
     ```

#### 127. **What are JavaScript `Generators`?**
   - **Answer:**
     Generators are functions that can be paused and resumed. They are declared with an asterisk (`*`) and use the `yield` keyword to pause execution and return a value.

     **Example:**
     ```javascript
     function* generator() {
       yield 1;
       yield 2;
       yield 3;
     }

     const gen = generator();
     console.log(gen.next().value); // 1
     console.log(gen.next().value); // 2
     console.log(gen.next().value); // 3
     ```

#### 128. **What is the `debounce` function in JavaScript?**
   - **Answer:**
     Debouncing is a technique used to ensure that a function is only called after a certain period of time has passed since the last time it was invoked. It’s useful for limiting the rate at which a function is executed, such as in the case of resizing or scrolling events.

     **Example:**
     ```javascript
     function debounce(func, delay) {
       let timeout;
       return function(...args) {
         clearTimeout(timeout);
         timeout = setTimeout(() => func.apply(this, args), delay);
       };
     }

     const log = debounce(() => console.log('Action'), 500);
     window.addEventListener('resize', log);
     ```

#### 129. **What is the `throttle` function in JavaScript?**
   - **Answer:**
     Throttling is a technique used to ensure that a function is only called at most once in a specified period of time. It’s useful for optimizing performance, such as limiting the frequency of scroll events.

     **Example:**
     ```javascript
     function throttle(func, limit) {
       let lastFunc;
       let lastRan;
       return function(...args) {
         if (!lastRan) {
           func.apply(this, args);
           lastRan = Date.now();
         } else {
           clearTimeout(lastFunc);
           lastFunc = setTimeout(() => {
             if ((Date.now() - lastRan) >= limit) {
               func.apply(this, args);
               lastRan = Date.now();
             }
           }, limit - (Date.now() - lastRan));
         }
       };
     }

     const log = throttle(() => console.log('Scroll event'), 1000);
     window.addEventListener('scroll', log);
     ```

#### 130. **What is the difference between `call`, `apply`, and `bind` in JavaScript?**
   - **Answer:**
     - **`call()`:** Invokes a function with a given `this` context and arguments provided individually.
     - **`apply()`:** Invokes a function with a given `this` context and arguments provided as an array.
     - **`bind()`:** Creates a new function that, when called, has its `this` context set to the provided value, with a given sequence of arguments.

     **Example:**
     ```javascript
     function greet(greeting, name) {
       console.log(`${greeting}, ${name}`);
     }

     greet.call(null, 'Hello', 'Alice'); // 'Hello, Alice'
     greet.apply(null, ['Hello', 'Bob']); // 'Hello, Bob'

     const greetAlice = greet.bind(null, 'Hello', 'Alice');
     greetAlice(); // 'Hello, Alice'
     ```

These questions cover more advanced JavaScript concepts, providing a deeper understanding of the language's intricacies and best practices.
