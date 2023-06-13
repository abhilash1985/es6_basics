# ES6 Basics
Javascript ES6 basic features

ES6 - https://www.w3schools.com/js/js_es6.asp

https://www.w3schools.com/js/js_object_maps.asp


ECMAScript 2015 was the second major revision to JavaScript.

ECMAScript 2015 is also known as ES6 and ECMAScript 6.

## 1) let

The let keyword allows you to declare a variable with block scope.

```
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
```

## 2) const

The const keyword allows you to declare a constant (a JavaScript variable with a constant value).

Constants are similar to let variables, except that the value cannot be changed.

```
var x = 10;
// Here x is 10
{
  const x = 2;
  // Here x is 2
}
// Here x is 10
```

## 3) Arrow Functions

Arrow functions allows a short syntax for writing function expressions.

```
// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;

const x = (x, y) => { return x * y };
```

## 4) The Spread (...) Operator

```
const q1 = ["Jan", "Feb", "Mar"];
const q2 = ["Apr", "May", "Jun"];
const q3 = ["Jul", "Aug", "Sep"];
const q4 = ["Oct", "Nov", "May"];

const year = [...q1, ...q2, ...q3, ...q4];
```

The ... operator can be used to expand an iterable into more arguments for function calls:

```
const numbers = [23,55,21,87,56];
let maxValue = Math.max(...numbers);
```

## 5) The For/Of Loop

The JavaScript for/of statement loops through the values of an iterable objects.

for/of lets you loop over data structures that are iterable such as Arrays, Strings, Maps, NodeLists, and more.

The for/of loop has the following syntax:

```
for (variable of iterable) {
  // code block to be executed
}

const cars = ["BMW", "Volvo", "Mini"];
let text = "";

for (let x of cars) {
  text += x + " ";
}
```

## 6) JavaScript Maps

Being able to use an Object as a key is an important Map feature.

```
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);
```

## 7) Set

```
// Create a Set
const letters = new Set();

// Add some values to the Set
letters.add("a");
letters.add("b");
letters.add("c");
```

## 8) Map Methods

```
Method	    Description
new Map()	Creates a new Map object
set()	    Sets the value for a key in a Map
get()	    Gets the value for a key in a Map
clear()	    Removes all the elements from a Map
delete()	Removes a Map element specified by a key
has()	    Returns true if a key exists in a Map
forEach()	Invokes a callback for each key/value pair in a Map
entries()	Returns an iterator object with the [key, value] pairs in a Map
keys()	    Returns an iterator object with the keys in a Map
values()	Returns an iterator object of the values in a Map
Property	Description
size	    Returns the number of Map elements
```

## 9) JavaScript Classes

JavaScript Classes are templates for JavaScript Objects.

Use the keyword class to create a class.

Always add a method named constructor():

```
class ClassName {
  constructor() { ... }
}

class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}

const myCar1 = new Car("Ford", 2014);
const myCar2 = new Car("Audi", 2019);
```

## 10) JavaScript Promises

A Promise is a JavaScript object that links "Producing Code" and "Consuming Code".

"Producing Code" can take some time and "Consuming Code" must wait for the result.

```
const myPromise = new Promise(function(myResolve, myReject) {
// "Producing Code" (May take some time)

  myResolve(); // when successful
  myReject();  // when error
});

// "Consuming Code" (Must wait for a fulfilled Promise).
myPromise.then(
  function(value) { /* code if successful */ },
  function(error) { /* code if some error */ }
);

Example Using a Promise
const myPromise = new Promise(function(myResolve, myReject) {
  setTimeout(function() { myResolve("I love You !!"); }, 3000);
});

myPromise.then(function(value) {
  document.getElementById("demo").innerHTML = value;
});
```

## 11) The Symbol Type

A JavaScript Symbol is a primitive datatype just like Number, String, or Boolean.

It represents a unique "hidden" identifier that no other code can accidentally access.

For instance, if different coders want to add a person.id property to a person object belonging to a third-party code, they could mix each others values.

Using Symbol() to create a unique identifiers, solves this problem:

```
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

let id = Symbol('id');
person[id] = 140353;
// Now person[id] = 140353
// but person.id is still undefined
```

## 12) Default Parameter Values

ES6 allows function parameters to have default values.

```
function myFunction(x, y = 10) {
  // y is 10 if not passed or undefined
  return x + y;
}
myFunction(5); // will return 15
```

## 13) Function Rest Parameter

The rest parameter (...) allows a function to treat an indefinite number of arguments as an array:

Example
```
function sum(...args) {
  let sum = 0;
  for (let arg of args) sum += arg;
  return sum;
}

let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
```

## 14) String.includes()

The includes() method returns true if a string contains a specified value, otherwise false:

Example
```
let text = "Hello world, welcome to the universe.";
text.includes("world")    // Returns true
```

## 15) String.startsWith()

The startsWith() method returns true if a string begins with a specified value, otherwise false:

Example
```
let text = "Hello world, welcome to the universe.";

text.startsWith("Hello")   // Returns true
```

## 16) String.endsWith()

The endsWith() method returns true if a string ends with a specified value, otherwise false:

Example
```
var text = "John Doe";
text.endsWith("Doe")    // Returns true
```

## 17) Array.from()

The Array.from() method returns an Array object from any object with a length property or any iterable object.

Example
Create an Array from a String:
```
Array.from("ABCDEFG")   // Returns [A,B,C,D,E,F,G]
```

## 18) Array keys()

The keys() method returns an Array Iterator object with the keys of an array.

Example
Create an Array Iterator object, containing the keys of the array:

```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const keys = fruits.keys();

let text = "";
for (let x of keys) {
  text += x + "<br>";
}
```

## 19) Array find()

The find() method returns the value of the first array element that passes a test function.

This example finds (returns the value of ) the first element that is larger than 18:

Example
```
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

## 20) Array findIndex()

The findIndex() method returns the index of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:

Example
```
const numbers = [4, 9, 16, 25, 29];
let first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

## 21) New Math Methods

ES6 added the following methods to the Math object:

```
Math.trunc()
Math.sign()
Math.cbrt()
Math.log2()
Math.log10()
```

## 22) The Math.trunc() Method

Math.trunc(x) returns the integer part of x:

Example
```
Math.trunc(4.9);    // returns 4
Math.trunc(4.7);    // returns 4
Math.trunc(4.4);    // returns 4
Math.trunc(4.2);    // returns 4
Math.trunc(-4.2);    // returns -4
```

## 23) The Math.sign() Method

Math.sign(x) returns if x is negative, null or positive:

Example
```
Math.sign(-4);    // returns -1
Math.sign(0);    // returns 0
Math.sign(4);    // returns 1
```

## 24) The Math.cbrt() Method

Math.cbrt(x) returns the cube root of x:

Example
```
Math.cbrt(8);    // returns 2
Math.cbrt(64);    // returns 4
Math.cbrt(125);    // returns 5
```

## 25) The Math.log2() Method

Math.log2(x) returns the base 2 logarithm of x:

Example
```
Math.log2(2);    // returns 1
```

## 26) New Number Properties

ES6 added the following properties to the Number object:

```
EPSILON
MIN_SAFE_INTEGER
MAX_SAFE_INTEGER
EPSILON Example
let x = Number.EPSILON;
```

## 27) MIN_SAFE_INTEGER Example

```
let x = Number.MIN_SAFE_INTEGER;
```

## 28) MAX_SAFE_INTEGER Example

```
let x = Number.MAX_SAFE_INTEGER;
```

## 29) New Number Methods

ES6 added 2 new methods to the Number object:

```
Number.isInteger()
Number.isSafeInteger()
```

## 30) The Number.isInteger() Method

The Number.isInteger() method returns true if the argument is an integer.

Example
```
Number.isInteger(10);        // returns true
Number.isInteger(10.5);      // returns false
```

## 31) The Number.isSafeInteger() Method

A safe integer is an integer that can be exactly represented as a double precision number.

The Number.isSafeInteger() method returns true if the argument is a safe integer.

Example
```
Number.isSafeInteger(10);    // returns true
Number.isSafeInteger(12345678901234567890);  // returns false
```

## 32) New Global Methods

ES6 added 2 new global number methods:

```
isFinite()
isNaN()
```

## 33) The isFinite() Method

The global isFinite() method returns false if the argument is Infinity or NaN.

Otherwise it returns true:

Example
```
isFinite(10/0);       // returns false
isFinite(10/1);       // returns true
```

## 34) The isNaN() Method

The global isNaN() method returns true if the argument is NaN. Otherwise it returns false:

Example
```
isNaN("Hello");       // returns true
```

## 35) Object entries()

Example
Create an Array Iterator, and then iterate over the key/value pairs:

```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const f = fruits.entries();

for (let x of f) {
  document.getElementById("demo").innerHTML += x;
}
```

The entries() method returns an Array Iterator object with key/value pairs:

```
[0, "Banana"]
[1, "Orange"]
[2, "Apple"]
[3, "Mango"]
```

The entries() method does not change the original array.

## 36) Modules

Modules are imported in two differen ways:

a) Import from named exports
Import named exports from the file person.js:

```
import { name, age } from "./person.js";
```

b) Import from default exports
Import a default export from the file message.js:

```
import message from "./message.js";
```

## 37) Object.entries()

Object.entries() makes it simple to use objects in loops:

Example
```
const fruits = {Bananas:300, Oranges:200, Apples:500};

let text = "";
for (let [fruit, value] of Object.entries(fruits)) {
  text += fruit + ": " + value + "<br>";
}
```

Object.values() are similar to Object.entries(), but returns a single dimension array of the object values:

## 38) JavaScript Async Functions

Waiting for a Timeout

```
async function myDisplay() {
  let myPromise = new Promise(function(myResolve, myReject) {
    setTimeout(function() { myResolve("I love You !!"); }, 3000);
  });
  document.getElementById("demo").innerHTML = await myPromise;
}

myDisplay();
```

## 39) JavaScript Asynchronous Iteration

ECMAScript 2018 added asynchronous iterators and iterables.

With asynchronous iterables, we can use the await keyword in for/of loops.

Example
```
for await () {}
```
JavaScript asynchronous iteration is supported in all modern browsers since January 2020:

## 40) JavaScript Promise.finally

ECMAScript 2018 finalizes the full implementation of the Promise object with Promise.finally:

Example
```
let myPromise = new Promise();

myPromise.then();
myPromise.catch();
myPromise.finally();
```

## 41) JavaScript Object Rest Properties

ECMAScript 2018 added rest properties.

This allows us to destruct an object and collect the leftovers onto a new object:

Example
```
let { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
x; // 1
y; // 2
z; // { a: 3, b: 4 }
```
Object rest properties is supported in all modern browsers since January 2020:

## 42) New JavaScript RegExp Features

ECMAScript 2018 added 4 new RegExp features:

```
. Unicode Property Escapes (\p{...})
. Lookbehind Assertions (?<= ) and (?<! )
. Named Capture Groups
. s (dotAll) Flag
```

The new RegExp features is supported in all modern browsers since June 2020:

## 43) JavaScript Threads

In JavaScript you use the Web Workers API to create threads.

Worker threads are used to execute code in the background so that the main program can continue execution.

Worker threads run simultaneously with the main program. Simultaneous execution of different parts of a program can be time-saving.

## 44) JavaScript Shared Memory

Shared memory is a feature that allows threads (different parts of a program) to access and update the same data in the same memory.

Instead of passing data between threads, you can pass a SharedArrayBuffer object that points to the memory where data is saved.

## 45) SharedArrayBuffer

A SharedArrayBuffer object represents a fixed-length raw binary data buffer similar to the ArrayBuffer object.

## 46) JavaScript Object fromEntries()

ES2019 added the Object method fromEntries() to JavaScript.

The fromEntries() method creates an object from iterable key / value pairs.

Example
```
const fruits = [
["apples", 300],
["pears", 900],
["bananas", 500]
];

const myObj = Object.fromEntries(fruits);
```

## 47) Optional catch Binding

From ES2019 you can omit the catch parameter if you don't need it:.

Example
Before 2019:

```
try {
// code
} catch (err) {
// code
}
```

After 2019:

```
try {
// code
} catch {
// code
}
```

## 48) JavaScript Array flat()

ES2019 added the Array flat() method to JavaScript.

The flat() method creates a new array by flattening a nested array.

Example
```
const myArr = [[1,2],[3,4],[5,6]];
const newArr = myArr.flat();
```

## 49) JavaScript Array flatMap()

ES2019 added the Array flatMap() method to JavaScript.

The flatMap() method first maps all elements of an array and then creates a new array by flattening the array.

Example
```
const myArr = [1, 2, 3, 4, 5, 6];
const newArr = myArr.flatMap((x) => x * 2);
```

## 50) Stable Array sort()

ES2019 revised the Array sort() method.

Before 2019, the specification allowed unstable sorting algorithms such as QuickSort.

After ES2019, browsers must use a stable sorting algorithm:

When sorting elements on a value, the elements must keep their relative position to other elements with the same value.

Example
```
const myArr = [
  {name:"X00",price:100 },
  {name:"X01",price:100 },
  {name:"X02",price:100 },
  {name:"X03",price:100 },
  {name:"X04",price:110 },
  {name:"X05",price:110 },
  {name:"X06",price:110 },
  {name:"X07",price:110 }
];
```

## 51) Revised JSON.stringify()

ES2019 revised the JSON stringify() method.

Before 2019, JSON could not stringify character encoded with \.

Example
```
let text = JSON.stringify("\u26D4");
```

Before ES2019, using JSON.stringify()JSON on UTF-8 code points (U+D800 to U+DFFF) returned broken Unicode characters like ���.

After this revision, strings with UTF-8 code points convert safely with JSON.stringify(), and back to the original using JSON.parse().

## 52) Separator Symbols

Line separators and paragraph separator symbols (\u2028 and \u2029) are now allowed in string literals.

Before 2019, these were treated as line terminators and resulted in error exceptions:

Example
```
// This is valid in ES2019:
let text = "\u2028";
```

## 53) Revised Function toString()

ES2019 revised the Function toString() method.

The toString() method returns a string representing the source code of a function.

From 2019, toString() must return the source code of the function including comments, spaces, and syntax details.

Before 2019, different browsers returned different variants of the function (like without comments and spaces). From 2019 the function should be returned exactly as it is written.

Example
```
function myFunction(p1, p2) {
  return p1 * p2;
}
```

## 54) The Nullish Coalescing Operator (??)

The ?? operator returns the first argument if it is not nullish (null or undefined).

Otherwise it returns the second.

Example
```
let name = null;
let text = "missing";
let result = name ?? text;
```

## 55) The Optional Chaining Operator (?.)

The Optional Chaining Operator returns undefined if an object is undefined or null (instead of throwing an error).

Example
```
const car = {type:"Fiat", model:"500", color:"white"};
let name = car?.name;
```

## 56) The &&= Operator

The Logical AND Assignment Operator is used between two values.

If the first value is true, the second value is assigned.

Logical AND Assignment Example
```
let x = 10;
x &&= 5;
```

## 57) The ||= Operator

The Logical OR Assignment Operator is used between two values.

If the first value is false, the second value is assigned.

Logical OR Assignment Example
```
let x = 10;
x ||= 5;
```

## 58) The ??= Operator

The Nullish Coalescing Assignment Operator is used between two values.

If the first value is undefined or null, the second value is assigned.

Nullish Coalescing Assignment Example
```
let x = 10;
x ??= 5;
```

## 59) JavaScript Numeric Separator (_)

ES2021 intoduced the numeric separator (_) to make numbers more readable:

Example
```
const num = 1_000_000_000;
```

## 60) JavaScript Array at()

ES2022 intoduced the array method at():

Examples
Get the third element of fruits:

```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits.at(2);
```

## 61) JavaScript Object Constructors

Example
```
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}
```

## 62) Object Types (Blueprints) (Classes)

The examples from the previous chapters are limited. They only create single objects.

Sometimes we need a "blueprint" for creating many objects of the same "type".

The way to create an "object type", is to use an object constructor function.

In the example above, function Person() is an object constructor function.

Objects of the same type are created by calling the constructor function with the new keyword:

```
const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");
```

## 63) JavaScript Object Prototypes

All JavaScript objects inherit properties and methods from a prototype.

In the previous chapter we learned how to use an object constructor:

Example
```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");
```
We also learned that you can not add a new property to an existing object constructor:

Example
```
Person.nationality = "English";
```

To add a new property to a constructor, you must add it to the constructor function:

Example
```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.nationality = "English";
}
```

Prototype Inheritance

All JavaScript objects inherit properties and methods from a prototype:

```
Date objects inherit from Date.prototype
Array objects inherit from Array.prototype
Person objects inherit from Person.prototype
The Object.prototype is on the top of the prototype inheritance chain:
```

Date objects, Array objects, and Person objects inherit from Object.prototype.

Adding Properties and Methods to Objects

Sometimes you want to add new properties (or methods) to all existing objects of a given type.

Sometimes you want to add new properties (or methods) to an object constructor.

Using the prototype Property
The JavaScript prototype property allows you to add new properties to object constructors:

Example
```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.nationality = "English";
```
The JavaScript prototype property also allows you to add new methods to objects constructors:

Example
```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.name = function() {
  return this.firstName + " " + this.lastName;
};
```

## 64) JavaScript Iterators

The iterator protocol defines how to produce a sequence of values from an object.

An object becomes an iterator when it implements a next() method.

The next() method must return an object with two properties:

```
. value (the next value)
. done (true or false)

value	The value returned by the iterator
        (Can be omitted if done is true)
done	true if the iterator has completed
        false if the iterator has produced a new value
```

## 65) Home Made Iterable

This iterable returns never ending: 10,20,30,40,.... Everytime next() is called:

Example
```
// Home Made Iterable
function myNumbers() {
  let n = 0;
  return {
    next: function() {
      n += 10;
      return {value:n, done:false};
    }
  };
}

// Create Iterable
const n = myNumbers();
n.next(); // Returns 10
n.next(); // Returns 20
n.next(); // Returns 30
```

## 66) Symbol Iterator

A JavaScript iterable is an object that has a Symbol.iterator.

The Symbol.iterator is a function that returns a next() function.

An iterable can be iterated over with the code: for (const x of iterable) { }

Example
```
// Create an Object
myNumbers = {};

// Make it Iterable
myNumbers[Symbol.iterator] = function() {
  let n = 0;
  done = false;
  return {
    next() {
      n += 10;
      if (n == 100) {done = true}
      return {value:n, done:done};
    }
  };
}
Now you can use for..of

for (const num of myNumbers) {
  // Any Code Here
}
```

The Symbol.iterator method is called automatically by for..of.

But we can also do it "manually":

Example
```
let iterator = myNumbers[Symbol.iterator]();

while (true) {
  const result = iterator.next();
  if (result.done) break;
  // Any Code Here
}
```

## 67) Interpolation

Template literals provide an easy way to interpolate variables and expressions into strings.

The method is called string interpolation.

The syntax is:
```
${...}

`This is ${index} number`
```

## 68) Variable Substitutions

Template literals allow variables in strings:

Example
```
let firstName = "John";
let lastName = "Doe";

let text = `Welcome ${firstName}, ${lastName}!`;
```

## 69) Expression Substitution

Template literals allow expressions in strings:

Example
```
let price = 10;
let VAT = 0.25;

let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;
```

## 70) HTML Templates

Example
```
let header = "Templates Literals";
let tags = ["template literals", "javascript", "es6"];

let html = `<h2>${header}</h2><ul>`;
for (const x of tags) {
  html += `<li>${x}</li>`;
}

html += `</ul>`;
```

## 71) Destructuring Assignment

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment