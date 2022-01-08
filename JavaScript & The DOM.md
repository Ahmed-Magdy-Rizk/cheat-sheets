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

#### example for null
``` 
var x = null;
console.log(x);
``` 
#### Returns:
``` 
null
```
#### example for undefined
``` 
var x;
console.log(x);
``` 
#### Returns:
``` 
undefined
```

## Implicit type coercion
```
"1" == 1
```
#### Returns:
```
true
```
```
"julia" + 1
```
#### Returns:
```
"julia1"
````
```
"Hello" % 10
```
#### Returns:
```java script
NaN

/*
- For JavaScript to use the modulus operator, it will cast both "Hello" and 10 into number data type. 10 already is a number, but what about "Hello"? When "Hello" is converted into a number, the result is NaN (Not a Number). You can see this by typing Number("Hello") in the console.
Therefore, the result of the operation is also NaN.
*/
```
## 










