# JavaScript

## Variables
There are three ways to declare a variable in JavaScript 
- var, let and const.
- var declarations are globally scoped or function scoped while let and const are block scoped.
- var variables can be updated and re-declared within its scope; let variables can be updated but not re-declared; const variables can neither be updated nor re-declared.
- They are all hoisted to the top of their scope. But while var variables are initialized with undefined, let and const variables are not initialized.
- While var and let can be declared without being initialized, const must be initialized during declaration.

 *inconclusion you shoud use ***const*** more than ***let*** more than ***var***.*
 
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

// Returns:
null
```
#### Example for undefined
```java script 
var x;
console.log(x);

// Returns:
undefined
```

## Implicit type coercion
#### Example
```java script
"1" == 1

// Returns:

true
```
#### Example
```java script
"julia" + 1

// Returns:

"julia1"
````
#### Example
```java script
"Hello" % 10

// Returns:

NaN

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

// Prints: "green"
```
#### Example
```java script
var eatsPlants = true;
var eatsAnimals = true;

var category = eatsPlants ? (eatsAnimals ? "omnivore" : "herbivore") : (eatsAnimals ? "carnivore" : "undefined");

console.log(category);

// Prints: "omnivore"
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
// Prints: You selected option 3.
```
#### another ecample for switch statment using default & break
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

// Prints: You've won tickets to the circus.
```
