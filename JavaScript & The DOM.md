# JavaScript

## Variables
There are three ways to declare a variable in JavaScript 
- let - It a new way to declare a variable in any scope - Global, Local, or Block. The value of this variable can be changed or reassigned anytime within its scope.
- const - It is also a way to declare constants in any scope - Global, Local, or Block. Once you are assigned a value to a const variable, the value of this variable CANNOT be changed or reassigned throughout the code.
- var - This is the old way of declaring variables in only two scope - Global, or Local. Variables declared with the var keyword can not have Block Scope. The value of this variable can be changed or reassigned anytime within its scope.

 *inconclusion you shoud use ***const*** more than ***let*** and rarely use ***var***.*
 
 ## Special characters
|Code|Character|
|--------|--------|
|    \\    |\ (backslash)|
|    \"    |'' (double quote)|
|    \n    |newline|
|    \t    |tab|

## Null, Undefined, and NaN data types
- null refers to the "value of nothing"
- undefined refers to the "absence of value".
- while Null refers to not a number.

#### Example for null
```java script 
var x = null;
console.log(x);

// Prints:
> null
```
#### Example for undefined
```java script 
var x;
console.log(x);

// Prints:
> undefined
```

## Implicit type coercion
#### Example
```java script
"1" == 1

// Returns:
> true
```
#### Example
```java script
"julia" + 1

// Returns:

> "julia1"
````
#### Example
```java script
"Hello" % 10

// Returns:
> NaN

/*
- For JavaScript to use the modulus operator, it will cast both "Hello" and 10 into number data type. 10 already is a number, but what about "Hello"? When "Hello" is converted into a number, the result is NaN (Not a Number). You can see this by typing Number("Hello") in the console.
Therefore, the result of the operation is also NaN.
*/
```
## false values in JavaScript.
Here’s the list of all of the falsy values:
1. the Boolean value false.
2. the null type.
3. the undefined type.
4. the number 0.
5. the empty string "".
6. the odd value NaN.

## Ternary operator
conditional ? (if condition is true) : (if condition is false)

#### Example
```java script
var isGoing = true;
var color = isGoing ? "green" : "red";
console.log(color);

// Prints: 
> "green"
```
#### Example
```java script
var eatsPlants = true;
var eatsAnimals = true;

var category = eatsPlants ? (eatsAnimals ? "omnivore" : "herbivore") : (eatsAnimals ? "carnivore" : "undefined");

console.log(category);

// Prints: 
> "omnivore"
```
## Switch Statement
#### Example
```java script
var option = 3;

switch (option) {
  case 1:
    console.log("You selected option 1.");
  case 2:
    console.log("You selected option 2.");
  case 3:
    console.log("You selected option 3.");
  case 4:
    console.log("You selected option 4.");
  case 5:
    console.log("You selected option 5.");
  case 6:
    console.log("You selected option 6.");
}
/*
Prints:
You selected option 3.
You selected option 4.
You selected option 5.
You selected option 6.
*/
```
#### same example for switch statment using break
```java script
var option = 3;

switch (option) {
  case 1:
    console.log("You selected option 1.");
    break;
  case 2:
    console.log("You selected option 2.");
    break;
  case 3:
    console.log("You selected option 3.");
    break;
  case 4:
    console.log("You selected option 4.");
  case 5:
    console.log("You selected option 5.");
  case 6:
    console.log("You selected option 6.");
}
// Prints: 
> You selected option 3.
```
#### another example for switch statment using default & break
```java script
var prize = "";
var winner = 0;

switch (winner) {
  case 1:
    prize += "a trip for two to the Bahamas and ";
  case 2:
    prize += "a four piece furniture set.";
    break;
  case 3:
    prize += "a smartwatch and ";
  default:
    prize += "tickets to the circus.";
}

console.log("You've won " + prize);

// Prints: 
> You've won tickets to the circus.
```
## Return
- Any function is always going to return some value back to the caller.
- If a return value is not specified, then the function will just return back undefined including **console.log** function.
- Return keyword has to job:
    1- stop the execution of a function.
    2- return a value back to the caller.
    
## Scope
- If an identifier is declared in global scope, it's available everywhere.
- If an identifier is declared in function scope, it's available in the function it was declared in (even in functions declared inside the function).
- When trying to access an identifier, the JavaScript Engine will first look in the current function. If it doesn't find anything, it will continue to the next outer function to see if it can find the identifier there. It will keep doing this until it reaches the global scope.
- Global identifiers are a bad idea. They can lead to bad variable names, conflicting variable names, and messy code.


#### Example.
```java script
var a = 1;
function x() {
  var b = 2;
  function y() {
    var c = 3;
    function z() {
      var d = 4;
    }
    z();
  }
  y();
}

x();
```
- [ ] anywhere in the script!.
- [ ] anywhere inside function x().
- [X] anywhere inside function y(). 
- [X] anywhere inside function z().

## Shadowing
- when a variable is declared in a certain scope having the same name defined on its outer scope and when we call the variable from the inner scope, the value assigned to the variable in the inner scope is the value that will be stored in the variable in the memory space.

#### Example
```java script
var bookTitle = "Le Petit Prince";
console.log (bookTitle);

function displayBookEnglish() {
 bookTitle = "The Little Prince";
  console.log (bookTitle);
}

displayBookEnglish();
console.log(bookTitle);

// Prints:
> "Le Petit Prince"
> "The Little Prince"
> "The Little Prince"
```

- to fix this we should declare a new variable in side the function.

```java script 
var bookTitle = "Le Petit Prince";
console.log (bookTitle);

function displayBookEnglish() {
  var bookTitle "The Little Prince";
  console.log(bookTitle);
}

displayBookEnglish();
console.log(bookTitle);
// Prints:
> "Le Petit Prince"
> "The Little Prince"
> "Le Petit Prince"
```
## Hoisting
- JavaScript hoists function declarations and variable declarations to the top of the current scope.
- Variable assignments are not hoisted.
- Declare functions and variables at the top of your scripts, so the syntax and behavior are consistent with each other.

#### Example
```java script
sayHi("Julia");

function sayHi(name) {
  console.log(greeting + " " + name);
  var greeting;
}

// Prints:
> undefined Julia
```
#### another example
```java script
sayHi("Julia");

function sayHi(name) {
  console.log(greeting + " " + name);
  var greeting = "Hello";
}

// Prints:
> undefined Julia
```
- The variable declaration is hoisted to the top of current scope (the top of the function). Remember that the declaration is hoisted, **not the assignment**. The code inside sayHi is equivalent to:
```java script
var greeting;
console.log(greeting + " " + name);
greeting = "Hello";
```




