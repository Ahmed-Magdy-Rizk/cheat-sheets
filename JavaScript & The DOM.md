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
## Return keyword
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

## Function Expression (anonymous function).
-  When a function is assigned to a variable. The function can be named, or anonymous. Use the variable name to call a function defined in a function expression.

#### Example
```java script
// anonymous function expression
var doSomething = function(y) {
  return y + 1;
};
```
```java script
// named function expression
var doSomething = function addOne(y) {
  return y + 1;
};
```
```java script
// for either of the definitions above, call the function like this:
doSomething(5);
```
```java script
// for either of the definitions above, call the function like this:
doSomething(5);

// Returns: 
> 6
```
- You can even pass a function into another function inline. This pattern is commonly used in JavaScript, and can be helpful streamlining your code.

#### Example
```java script
// function declaration that takes in two arguments: a string & another function.
// notice that we put the value (2) in the first function for the next function
function emotions(myString, myFunc) {
    console.log("I am " + myString + ", " + myFunc(2));
}
// calling the function
emotions("happy", function(num) {
    var sound = "";
    for (let i = 0; i < num; i++) {
        sound += "ha";
    }
    return sound + "!";
});

// Prints: 
> I am happy, haha!
```

## Array
### push() method
- You can use the push() method to add elements to the end of an array.
- with the push() method you need to pass the value of the element you want to add to the end of the array.
- push() method returns the length of the array after an element has been added.

#### Example
```java sript
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];

donuts.push("powdered"); // pushes "powdered" onto the end of the `donuts` array

// Returns: 
> 7
// donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"]
```

### pop() method
- you can use the pop() method to remove elements from the end of an array.
- pop() returns the element that has been removed in case you need to use it.

#### Example
```java script
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];
donuts.pop(); // the `pop()` method returns "powdered" because "powdered" was the last element on the end of `donuts` array

// Returns: 
> "powdered"
```

### splice() method
- You can use splice() method to add and remove elements from anywhere within an array.
- Following is the syntax of splice() method: 
    arrayName.splice(arg1, arg2, item1, ....., itemX); where,
    - arg1 = Mandatory argument. Specifies the starting index position to add/remove items.
    - arg2 = Optional argument. Specifies the count of elements to be removed. **If set to 0, no items will be removed**.
    - item1, ....., itemX are the items to be added at index position arg1
 
- splice() method returns the item(s) that were removed.

#### Example
```java script
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"];
donuts.splice(1, 1, "chocolate cruller", "creme de leche"); // removes "chocolate frosted" at index 1 and adds "chocolate cruller" and "creme de leche" starting at index 1

// Returns: 
> ["chocolate frosted"]
// donuts array after calling the splice() method: ["glazed", "chocolate cruller", "creme de leche", "Boston creme", "glazed cruller"]
```
### join() method
- The join() method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string.

#### Example 
```java script 
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Prints: 
> "Fire,Air,Water"

console.log(elements.join(''));
// Prints: 
> "FireAirWater"

console.log(elements.join('-'));
// Prints: 
> "Fire-Air-Water"
```

### forEach() method
- The forEach() method gives you an alternative way to iterate over an array, and manipulate each element in the array with an inline function expression.
- The function that you pass to the forEach() method can take up to three parameters:
    1- (element) The current element being processed in the array.
    2- (index)(Optional) The index of element in the array.
    3- (array) (Optional) The array forEach() was called upon.
    
#### Example
```java script
//loop over the following array and add 100 to each of the values if the value is divisible by 3.
var test = [1, 2, 3, 4, 5, 6, 7, 8, 9];

// Write your code here
test.forEach(function(element, index) {
    if (element % 3 === 0) {
        test[index] += 100;
    }
});

console.log(test);

// Prints
> [ 1, 2, 103, 4, 5, 106, 7, 8, 109 ]
```
