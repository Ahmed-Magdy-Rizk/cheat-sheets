-	[Variables](https://github.com/Ahmed-Magdy-Rizk/cheat-sheets/edit/main/JavaScript%20&%20The%20DOM.md##Variables)
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

// Prints: null
```
#### Example for undefined
```java script 
var x;
console.log(x);

// Prints: undefined
```

## Implicit type coercion
#### Example
```java script
"1" == 1

// Returns: true
```
#### Example
```java script
"julia" + 1

// Returns: "julia1"
````
#### Example
```java script
"Hello" % 10

// Returns: NaN

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

// Prints: You've won tickets to the circus.
```
## Return keyword
- Any function is always going to return some value back to the caller.
- If a return value is not specified, then the function will just return back undefined including **console.log** function.
- Return keyword has to job:
    1. stop the execution of a function.
    2. return a value back to the caller.
    
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
// "Le Petit Prince"
// "The Little Prince"
// "The Little Prince"
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
// "Le Petit Prince"
// "The Little Prince"
// "Le Petit Prince"
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

// Prints: undefined Julia
```
#### another example
```java script
sayHi("Julia");

function sayHi(name) {
  console.log(greeting + " " + name);
  var greeting = "Hello";
}

// Prints: undefined Julia
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

// Returns: 6
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

// Prints: I am happy, haha!
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

// Returns: 7
// donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"]
```

### pop() method
- you can use the pop() method to remove elements from the end of an array.
- pop() returns the element that has been removed in case you need to use it.

#### Example
```java script
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];
donuts.pop(); // the `pop()` method returns "powdered" because "powdered" was the last element on the end of `donuts` array

// Returns: "powdered"
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

// Returns: ["chocolate frosted"]
// donuts array after calling the splice() method: ["glazed", "chocolate cruller", "creme de leche", "Boston creme", "glazed cruller"]
```
### join() method
- The join() method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string.

#### Example 
```java script 
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Prints: 
// "Fire,Air,Water"

console.log(elements.join(''));
// Prints: 
// "FireAirWater"

console.log(elements.join('-'));
// Prints: 
// "Fire-Air-Water"
```

### forEach() method
- The forEach() method gives you an alternative way to iterate over an array, and manipulate each element in the array with an inline function expression.
- The function that you pass to the forEach() method can take up to three parameters:
    1. (element) The current element being processed in the array.
    2. (index)(Optional) The index of element in the array.
    3. (array) (Optional) The array forEach() was called upon.
    
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

// Prints: [ 1, 2, 103, 4, 5, 106, 7, 8, 109 ]
```

### map() method
- With the map() method, you can take an array, perform some operation on each element of the array, and return a new array.

#### Example
```java script
var myArray = [1, 2, 3, 4, 5];
var newArray = myArray.map(function(elem) {
   elem = elem + 100;
   return elem;
});

console.log(newArray);
console.log(myArray);

// Prints:
// [ 101, 102, 103, 104, 105 ]
// [ 1, 2, 3, 4, 5 ]
 ```
 
# The DOM
## Selecting Elements By ID, classes and tags.
### Selecting An Element By ID
 - document.getElementById();.
 - we're passing 'footer', not '#footer'. It already knows that it's searching for an ID (its name is "getElementById", for a reason!).

#### Example
```java script
document.getElementById('footer');
 
// Returns: <div id="main">…</div>
 
```
### Selecting Multiple Elements At Once (classes and tags)
  - document.getElement**s**ByClassName();
  - document.getElement**s**ByTagName();
  - they return *HTMLCollection* **not** an array.
  - Beware of the S!

#### Example
```java script
document.getElementsByClassName('brand-color');
 
// Returns: HTMLCollection []

```

#### Example
```java script
// 
document.getElementsByTagName('p');
 
// Returns: HTMLCollection(28)

```
### The querySelector Method
- .querySelector() Returns A Single Element *the first element*.
- unlike .getElementsByClassName() and .getElementsByTagName() both return a list of multiple elements, using .querySelector() with a class selector or a tag selector will still only return the first item it finds.
  
#### Example
```java script
// find and return the element with an ID of "header"
document.querySelector('#header');

// find and return the FIRST element with the class "header"
document.querySelector('.header');

// find and return the FIRST <header> element
document.querySelector('header');
 
// Returns: only the FIRST element you provided

```
#### another example
```java script
document.querySelector('p.callout'); 

// Returns: the first paragraph element that also has a class of: callout
```
### The querySelectorAll Method
- Returns a NodeList *not an array* of all elements with a certain class or all of one type of element (e.g. all <tr> tags).
- is possible to loop over a NodeList with either its .forEach() method, or the humble for loop.
 
#### Example
```java script
document.querySelectorAll('.articles p'); 

// Returns: all paragraph elements that are descendents of elements that have the class: articles 
```
#### Another example
```java script
const allHeaders = document.querySelectorAll('header');

for(let i = 0; i < allHeaders.length; i++){
    console.dir(allHeaders[i]);
}
```
## Updating & Creating content
### Update Existing Content (.innerHTML, .textContent, .innerText)
- The .innerHTML property returns the HTML content inside the selected element (i.e. between the tags).
- here's also the rarely used .outerHTML property. .outerHTML represents the HTML element itself, as well as its children.
 
#### Example
```java script
<h1 id="pick-me">Greetings To <span>All</span>!</h1>

const innerResults = document.querySelector('#pick-me').innerHTML;
console.log(innerResults); 

// Prints:  the string: "Greetings To <span>All</span>!"

const outerResults = document.querySelector('#pick-me').outerHTML;
console.log(outerResults);

// Prints: "<h1 id="pick-me">Greetings To <span>All</span>!</h1>"
```
 
- The .textContent property will:
    1. set the text content of an element and all its descendants
    2. return the text content of an element and all its descendants
- passing text that contains HTML characters to .textContent **will not display the content as HTML**. Instead, it will still display everything as text - even the HTML characters!
 
 - If you'd like to update an element, including its HTML, then you need to use the .innerHTML property
                                     
#### Example
```java script
myElement.textContent = 'The <strong>Greatest</strong> Ice Cream Flavors';
// Returns: The <strong>Greatest</strong> Ice Cream Flavors

myElement.innerHTML = 'The <strong>Greatest</strong> Ice Cream Flavors';
// Returns: The **Greatest** Ice Cream Flavors
```

- .textContent completely **ignores** any CSS styling and returns all of the element's HTML just as it's listed in the HTML
- .innerText property will take CSS styling into consideration and will return the text that is visibly rendered on the page.

#### Example
- https://www.youtube.com/watch?v=x_F1R-VGxeE

### Add New Page Content
- .createElement() to create new elements
- .appendChild() to add a child element to a parent element as its last child
- .insertAdjacentHTML() to put HTML text anywhere around an element.

**Some important things to note are:**

- if an element already exists in the DOM and this element is passed to .appendChild(), the .appendChild() method will move it rather than duplicating it.
- an element's .textContent property is used more often than creating a text node with the .createTextNode() method.
- the .insertAdjacentHTML() method's second argument has to be text, you can't pass an element

#### Example
```java script
const myPara = document.createElement('p');

myPara.textContent = 'I am the text for the paragraph!';
document.body.appendChild(myPara);
 
```
#### Example
```java script
// beforebegin 
<p>
    // afterbegin
    Existing text/HTML content
    // beforeend
</p>
// afterend
 
const mainHeading = document.querySelector('#main-heading');
const htmlTextToAdd = '<h2>Skydiving is fun!</h2>';

mainHeading.insertAdjacentHTML('afterend', htmlTextToAdd);

// Returns: h2 element as a usual header(wihtout the angels brackets) after the h1
```

### Style Page Content
- .style.<property>, you can only modify one CSS style at a time.

#### Example
```java script
const mainHeading = document.querySelector('h1');

mainHeading.style.color = 'blue';
mainHeading.style.backgroundColor = 'orange';
mainHeading.style.fontSize = '3.5em';
```
 
- you can use the .style.cssText property to set multiple CSS styles at once!
- you write the CSS styles just as you would in a stylesheet; so you write font-size rather than fontSize. This is different than using the individual .style.<property> way.
- .style.cssText will **overwrite** anything that's already in the .style attribute
 
#### Example
```java script
const mainHeading = document.querySelector('h1');

mainHeading.style.cssText = 'color: blue; background-color: orange; font-size: 3.5em';
```
#### another example
```java script
<p id="quizzing-quizzes" style="color: orange;">Howdy</p>

document.querySelector('#quizzing-quizzes').style.cssText = 'width: 30px; textDecoration: underline;';
 
// Returns: Only the width styling will be in the element's style attribute. The .style.cssText will overwrite anything that's already in the .style attribute 
// (which removes the color styling),
// The textDecoration rule is misspelled and should be text-decoration, so it gets dropped.
```
 
- The .className property returns a space-separated string of the classes.
- you can convert the space-separated string into an array using the JavaScript string method .split() and manipulate it using any method like .push() or .pop()

#### Example
```java script
<h1 id="main-heading" class="ank-student jpk-modal">Learn Web Development at Udacity</h1>
const mainHeading = document.querySelector('#main-heading');

// store the list of classes in a variable
const listOfClasses = mainHeading.className;

// Returns: the string "ank-student jpk-modal"

const arrayOfClasses = listOfClasses.split(' ');
console.log(arrayOfClasses);

// Returns: logs out the array of strings ["ank-student", "jpk-modal"] 
```
 
- alternatively you can use The .classList Property
- Returns A DOMTokenList.
- The .classList property has a number of properties of its own. Some of the most popularly used ones are:

   1. .add() - to add a class to the list
   2. .remove() - to remove a class from the list
   2. .toggle() - to add the class if it doesn't exists or remove it from the list if it does already exist
   4. .contains() - returns a boolean based on if the class exists in the list or not
 
#### Example
```java script
<h1 id="main-heading" class="ank-student jpk-modal">Learn Web Development at Udacity</h1>
 
 const mainHeading = document.querySelector('#main-heading');

// store the list of classes in a variable
const listOfClasses = mainHeading.classList;

console.log(listOfClasses);

// logs out the DOMTokenList ["ank-student", "jpk-modal"] 
```

#### Example for the properties
- https://www.youtube.com/watch?v=SIjgdT1O2Ns

## Working with Browser Events
### Adding An Event Listener
 - .addEventListener() method will let us listen for events and respond to them!
 - an event listener needs three things:
    1. an event target - this is called the target.
    2. the type of event to listen for - this is called the type.
    3. function to run when the event occurs - this is called the listener.
 
#### Example
 ```java script
const mainHeading = document.querySelector('h1');
 
mainHeading.addEventListener('click', function () {
  console.log('The heading was clicked!');
});
 ```
 
### Remove an Event Listener
 - .removeEventListener() method will let us remove an evelnt listener
 - an event listener needs three things:
    1. an event target - this is called the target
    2. the type of event to listen for - this is called the type
    3. function to run when the event occurs - this is called the listener
- .removeEventListener() method requires you to pass **the same exact listener function** to it as the one you passed to .addEventListener().
 
 #### Example 
 ```java script
 function myEventListeningFunction() {
    console.log('howdy');
}

// adds a listener for clicks, to run the `myEventListeningFunction` function
document.addEventListener('click', myEventListeningFunction);

// immediately removes the click listener that should run the `myEventListeningFunction` function
document.removeEventListener('click', myEventListeningFunction);
 
// This code will successfully add and then remove an event listener
 ```
- Now, why does this work? It works because both .addEventListener() and .removeEventListener:

    1. have the same target
    2. have the same type
    3. **and pass the exact same listener**
 
#### another Example
```java script
 // adds a listener for clicks, to run the `myEventListeningFunction` function
document.addEventListener('click', function myEventListeningFunction() {
    console.log('howdy');
});

// immediately removes the click listener that should run the `myEventListeningFunction` function
document.removeEventListener('click', function myEventListeningFunction() {
    console.log('howdy');
});
 
// it does not remove the event listener
 ``` 
- This code does not successfully remove the event listener. Again, why does this not work?

    1. both .addEventListener() and .removeEventListener have the same target
    2. both .addEventListener() and .removeEventListener have the same type
    3. .addEventListener() and .removeEventListener have their own distinct listener functions...they do not refer to the exact same function
 
### Phases of an Event
- There are three different phases during the lifecycle of an event. They are:
    1. the capturing phase
    2. the at target phase
    3. and the bubbling phase
- when .addEventListener() is called with only two arguments, the third method defaults to using the bubbling phase.

 #### Example
 - The code below uses .addEventListener() with only two arguments, so it will invoke the listener during the bubbling phase:
  ```js
 document.addEventListener('click', function () {
   console.log('The document was clicked');
});
 ```
- However, in this code, .addEventListener() is called with three arguments with the third argument being true (meaning it should invoke the listener earlier, during the capturing phase!).
```js
 document.addEventListener('click', function () {
   console.log('The document was clicked');
}, true);
 ```
- you can .preventDefault() method to prevent the default action from occurring!
 
#### Example
 ```js
const links = document.querySelectorAll('a');
const thirdLink = links[2];

thirdLink.addEventListener('click', function (event) {
    event.preventDefault();
    console.log("Look, ma! We didn't navigate to a new page!");
});
``` 
 
## Performance
### Add Page Content Efficiently
- performance.now() returns a timestamp that is measured in milliseconds
- hese are the steps to use performance.now() to measure the speed of your code:
	1. use performance.now() to get the initial start time for the code
    2. run the code you want to test
    3. execute performance.now() to get another time measurement
    4. subtract the initial time from the final time
#### Example
```js
const startingTime = performance.now();

const myCustomDiv = document.createElement('div');

for (let i = 1; i <= 200; i++) {
  const newElement = document.createElement('p');
  newElement.innerText = 'This is paragraph number ' + i;

  myCustomDiv.appendChild(newElement);
}

document.body.appendChild(myCustomDiv);

const endingTime = performance.now();
console.log('This code took ' + (endingTime - startingTime) + ' milliseconds.');
 
// Prints: This code took 3 milliseconds.
```
- We can use the .createDocumentFragment() method to create an empty DocumentFragment object.
#### Example
```js
const fragment = document.createDocumentFragment();  // ← uses a DocumentFragment instead of a <div>

for (let i = 0; i < 200; i++) {
    const newElement = document.createElement('p');
    newElement.innerText = 'This is paragraph number ' + i;

    fragment.appendChild(newElement);
}

document.body.appendChild(fragment); // reflow and repaint here -- once!
```
