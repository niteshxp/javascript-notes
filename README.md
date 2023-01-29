# javascript-notes

#### 1. VAR vs LET vs CONST :

<details> <summary> Click here </summary> In JavaScript, the "var", "let", and "const" keywords are used to declare variables. Each keyword has a specific behavior and use case:

* "var": Variables declared with the "var" keyword are function scoped, meaning they are only accessible within the function in which they are declared. If a variable is declared without a keyword, it is automatically assigned to the global scope. Variables declared with "var" are also subject to hoisting, which means that they are moved to the top of their scope and are available before their actual declaration.

* "let": Variables declared with the "let" keyword are block scoped, meaning they are only accessible within the block in which they are declared. This is similar to "var", but the variable is only accessible within the curly braces {}. "let" also does not support hoisting.

* "const": Variables declared with the "const" keyword are also block scoped, but they cannot be reassigned after they are declared. This means that the value of a variable declared with "const" must be set at the time of declaration and cannot be changed later on.

In general, it's recommended to use "let" when you know the variable will be reassigned, and "const" when you know the variable will not be reassigned. This makes your code more readable and maintainable.

In practice, "var" is being phased out and replaced by "let" and "const" as they are considered more robust and less prone to errors. With "let" and "const" you can also avoid some of the issues that may occur with hoisting.
 </details>

#### 2. HOISTING : 

<details> <summary> Click here </summary>In JavaScript, hoisting is a behavior where variable and function declarations are moved to the top of their scope. This means that variables and functions declared with the "var" keyword are available before their actual declaration.

For example, in the following code:
```
console.log(x);
var x = 5;

```
The variable x is hoisted to the top of the scope and is undefined, so the output will be "undefined".

Similarly, in the case of function declaration:
```
hoistedFunction();
function hoistedFunction() {
  console.log("I'm a hoisted function!");
}

```
The function hoistedFunction is hoisted to the top of the scope and it can be called before its declaration

This behavior can lead to unexpected results and can make code more difficult to understand. For example, a variable declared in a function may be accessible before the function is called.

ES6 introduced the "let" and "const" keywords, which do not support hoisting, variables declared with them are accessible only within the block they are declared, and they will throw a reference error if you try to access them before their declaration.

It's a best practice to always declare variables at the top of their scope, in order to avoid confusion and potential bugs related to hoisting.
</details>

#### 3. SCOPES :
<details> <summary> Click here </summary>
In JavaScript, a scope is the context in which a variable or function is defined and accessible. There are two types of scopes in JavaScript: global scope and local scope.

Global Scope: Variables and functions declared in the global scope are accessible from anywhere in the code, including inside functions and other scopes. Variables declared without the "var", "let", or "const" keywords are automatically assigned to the global scope.

Local Scope: Variables and functions declared within a function or block (using curly braces) are only accessible within that function or block. They are said to have a local scope.

JavaScript uses a concept called scope chain to determine the scope of a variable or function. When a variable or function is accessed, the JavaScript engine starts with the innermost scope and works its way outward, checking for the variable or function in each scope. This process is called scope resolution. If the variable or function is not found in the innermost scope, the engine moves on to the next outer scope and so on, until it reaches the global scope.

The "let" and "const" keywords are block scoped, which means they are only accessible within the block they are declared, while "var" is function scoped, which means they are only accessible within the function they are declared.

Understanding scope is important when writing JavaScript code, as it can help prevent naming conflicts and unintended consequences. For example, it is important to be aware of the scope of variables when working with closures, which are a powerful feature of JavaScript that allows inner functions to access variables from the parent function's scope.
</details>

#### 4. DATA TYPES :
<details> <summary> Click here </summary>
JavaScript has several built-in data types, including:

* Number: for numeric values (e.g. 42, 3.14)
* String: for text values (e.g. "hello world")
* Boolean: for true/false values
* Symbol: for unique and immutable identifiers
* Object: for complex data structures
* Function: for executable code
* undefined: for variables that have been declared but have not been assigned a value
* Additionally, JavaScript also has a special value null, which represents the intentional absence of any object value.
</details>

#### 5. ASYNC NATURE OF JAVASCRIPT :
<details> <summary> Click here </summary>
JavaScript is single-threaded, which means that it can only process one task at a time. However, it uses an event loop to handle asynchronous tasks, such as user input, network requests, and timers. The event loop allows JavaScript to continue executing code while it is waiting for an asynchronous task to complete.

In JavaScript, asynchronous code is typically executed using callback functions, promises, and async/await.

<li> Callbacks: A callback function is passed as an argument to another function, and is executed after some kind of event or operation has completed. For example, setTimeout() function takes a callback function as an argument and calls it back after a specified amount of time has elapsed.

<li> Promises: A promise is an object that represents the eventual completion or failure of an asynchronous operation. Promises are used to handle asynchronous code in a more structured and predictable way.

<li> Async/Await: The `async` and `await` keywords are used to write asynchronous code that looks and behaves like synchronous code. The async keyword is used before a function definition to indicate that the function should return a promise. The await keyword is used before an asynchronous operation to pause the execution of the function until the promise is resolved.

<li> In JavaScript, the event loop is constantly checking the message queue for new messages to process. These messages could be user interactions, network responses, timers, or other async events. As soon as the execution stack is empty, the event loop will take the first message from the queue and will push it on the execution stack to be executed.

This allows JavaScript to handle multiple async events simultaneously without freezing the user interface or blocking other scripts.

Knowing and understanding the asynchronous nature of JavaScript is important to write efficient and non-blocking code, which is crucial for web applications with good performance.
</details>

#### 6. CALLBACKS :
<details> <summary> Click here </summary>
A callback function in JavaScript is a function that is passed as an argument to another function, and is executed after some kind of event or operation has completed.

Here is an example of a simple callback function:
```
function myFunction(callback) {
    // Do some work
    callback();
}

function myCallback() {
    console.log("Callback function has been called!");
}

myFunction(myCallback); 
// Output: "Callback function has been called!"

```
Here is another example using setTimeout():
```
function myFunction() {
    console.log("I am called immediately");
    setTimeout(function() {
        console.log("I am called after 2 seconds");
    }, 2000);
}

myFunction();

```

In the above example, the function passed to setTimeout() is a callback function because it is called back by setTimeout() after the specified time has elapsed. The output would be "I am called immediately" immediately and "I am called after 2 seconds" after 2 seconds.

Callbacks are often used in JavaScript for asynchronously executing code, for example, to handle responses from an API call, to handle the completion of a task, or to handle user inputs.

Another example is using callbacks in event listeners where we pass a callback function as a parameter to the event listener function.
```
document.getElementById("myBtn").addEventListener("click", function() {
    alert("Button was clicked");
});
```
In the above example, the function passed as the second argument to the addEventListener method is a callback function that is called when the button is clicked.

</details>

#### 7. CALLBACK HELL :
<details> <summary> Click here </summary>
Callback hell, also known as "Pyramid of Doom," is a term used to describe a situation where a large number of nested callback functions make the code difficult to read and understand. This can happen when dealing with multiple asynchronous operations that are dependent on each other.

Here is an example of callback hell:
```
step1(function (value1) {
  step2(value1, function (value2) {
    step3(value2, function (value3) {
      step4(value3, function (value4) {
        // Do something with value4
      });
    });
  });
});
```
As the number of nested callbacks increases, the code becomes harder to read and understand. It also becomes harder to add error handling, as it needs to be duplicated at every level of the nesting.

To avoid callback hell, there are several patterns that can be used such as:

<li>Using promises and promise chaining
<li>Using async/await
<li>Using control flow libraries like async.js

Promises and async/await allows you to write async code in a way that looks more like sync code, which is easier to read and understand. Control flow libraries like async.js allows you to organize async code in a way that is more readable and manageable.

It's important to keep in mind that the key is to make your code as readable and maintainable as possible, and that the solution will depend on the specific use case.
</details>

#### 8. PROMISES :
<details> <summary> Click here </summary>
A promise in JavaScript is an object that represents the eventual completion or failure of an asynchronous operation. Promises provide a way to handle asynchronous code in a more structured and predictable way.

A promise has a state, which can be one of:

* "pending" (initial state)
* "fulfilled" (operation completed successfully)
* "rejected" (operation failed)

A promise has two main methods:

* then(): is called when the promise is fulfilled and allows you to register callbacks to handle the resolved value
* catch(): is called when the promise is rejected and allows you to register a callback to handle the rejection reason

Here is an example of using promises to handle an asynchronous operation:
```
let promise = new Promise(function(resolve, reject) {
    setTimeout(() => resolve("Hello World"), 2000);
});

promise.then(function(value) {
    console.log(value); // Output: "Hello World"
}).catch(function(error) {
    console.log(error);
});
```
In the example above, the promise is created with a function that takes two arguments: resolve and reject. The function sets a timeout to resolve the promise with the value "Hello World" after 2 seconds. The then() method is used to register a callback that logs the resolved value "Hello World" to the console. The catch() method is used to handle any errors that may occur during the promise execution.

Promise chaining allows you to chain multiple promises together, where the return value of one promise is passed as the input to the next promise in the chain. This makes the code more readable and manageable.

```
let promise1 = new Promise(function(resolve, reject) {
    setTimeout(() => resolve("Hello"), 2000);
});

let promise2 = new Promise(function(resolve, reject) {
    setTimeout(() => resolve("World"), 2000);
});

promise1.then(function(value) {
    console.log(value); // Output: "Hello"
    return promise2;
}).then(function(value) {
    console.log(value); // Output: "World"
});

```

In the example above, promise1 and promise2 are created and resolved with the values "Hello" and "World" respectively. The first then() method logs the resolved value of promise1 and returns promise2. The second then() method logs the resolved value of promise2.

Promises are a powerful tool to handle asynchronous code in JavaScript and they are supported by most modern browsers and JavaScript environments.
</details>

#### 9. ASYNC AND AWAIT:
<details> <summary> Click here </summary>
"async" and "await" are keywords in JavaScript that allow for asynchronous programming.

Example using "async":
```
async function fetchData() {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  return data;
}
```

Example using "await":

```async function fetchDataAndProcess() {
  const data = await fetchData();
  console.log(data);
}
```

In these examples, the `fetchData` function is declared as `async`, meaning it returns a Promise and can be "awaited". The `fetchDataAndProcess` function "awaits" the resolved value of the `fetchData` Promise and logs the returned data to the console.
</details>

#### 10. DESTRUCTURING AND SPREADING:
<details> <summary> Click here </summary>
 Destructuring is a feature in JavaScript that allows you to extract values from arrays or objects and assign them to variables. It allows you to extract data from arrays or objects and assign them to variables in a more concise and readable way.

For example, instead of using the traditional method of accessing an object's properties (object.property), you can use destructuring to assign the value of the property to a variable:

```
 const obj = {x:1, y:2, z:3};
const {x, y, z} = obj;
console.log(x, y, z); // 1 2 3
```
 
 Spreading is a feature in JavaScript that allows you to spread elements of an array or object into a new array or object. It allows you to copy or concatenate arrays and objects in a more concise and readable way.

For example, you can use the spread operator to concatenate two arrays:
 ```const a = [1, 2, 3];
const b = [4, 5, 6];
const c = [...a, ...b];
console.log(c); // [1, 2, 3, 4, 5, 6]
```
 or to clone the object:
 ```
 const obj = {x:1, y:2, z:3};
const newObj = {...obj};
```
