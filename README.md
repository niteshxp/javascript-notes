# javascript-notes

#### VAR vs LET vs CONST :

<details> <summary> Click here </summary> In JavaScript, the "var", "let", and "const" keywords are used to declare variables. Each keyword has a specific behavior and use case:

* "var": Variables declared with the "var" keyword are function scoped, meaning they are only accessible within the function in which they are declared. If a variable is declared without a keyword, it is automatically assigned to the global scope. Variables declared with "var" are also subject to hoisting, which means that they are moved to the top of their scope and are available before their actual declaration.

* "let": Variables declared with the "let" keyword are block scoped, meaning they are only accessible within the block in which they are declared. This is similar to "var", but the variable is only accessible within the curly braces {}. "let" also does not support hoisting.

* "const": Variables declared with the "const" keyword are also block scoped, but they cannot be reassigned after they are declared. This means that the value of a variable declared with "const" must be set at the time of declaration and cannot be changed later on.

In general, it's recommended to use "let" when you know the variable will be reassigned, and "const" when you know the variable will not be reassigned. This makes your code more readable and maintainable.

In practice, "var" is being phased out and replaced by "let" and "const" as they are considered more robust and less prone to errors. With "let" and "const" you can also avoid some of the issues that may occur with hoisting.
 </details>

#### HOISTING : 

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

#### SCOPES :
<details> <summary> Click here </summary>
In JavaScript, a scope is the context in which a variable or function is defined and accessible. There are two types of scopes in JavaScript: global scope and local scope.

Global Scope: Variables and functions declared in the global scope are accessible from anywhere in the code, including inside functions and other scopes. Variables declared without the "var", "let", or "const" keywords are automatically assigned to the global scope.

Local Scope: Variables and functions declared within a function or block (using curly braces) are only accessible within that function or block. They are said to have a local scope.

JavaScript uses a concept called scope chain to determine the scope of a variable or function. When a variable or function is accessed, the JavaScript engine starts with the innermost scope and works its way outward, checking for the variable or function in each scope. This process is called scope resolution. If the variable or function is not found in the innermost scope, the engine moves on to the next outer scope and so on, until it reaches the global scope.

The "let" and "const" keywords are block scoped, which means they are only accessible within the block they are declared, while "var" is function scoped, which means they are only accessible within the function they are declared.

Understanding scope is important when writing JavaScript code, as it can help prevent naming conflicts and unintended consequences. For example, it is important to be aware of the scope of variables when working with closures, which are a powerful feature of JavaScript that allows inner functions to access variables from the parent function's scope.
</details>

#### DATA TYPES :
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
