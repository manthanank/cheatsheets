---
title: JavaScript
date: "2022-1-3"
description: "Complete JavaScript Guide."
tags: ["javascript"]
---

**JavaScript** is a scripting language. It is object-based, lightweight, cross-platform translated language. It is widely used for client-side validation.

## Syntax

```javascript
<script>
 JavaScript code
</script>
```

## Add javascript

**JavaScript in `<head>`**

```html
<!DOCTYPE html>
<html>
<head>
<script>
    //code
</script>
</head>
<body>
<h2>Heading</h2>
</body>
</html>
```

**JavaScript in `<body>`**

```html
<!DOCTYPE html>
<html>
<body>

<h2>Heading</h2>

<script>
    //code
</script>

</body>
</html>
```

**External JavaScript** -

```javascript
// code
```

```html
<!DOCTYPE html>
<html>
<body>

<h2>Heading</h2>

<script src="myScript.js"></script>
</body>
</html>
```

## JavaScript Output

### JavaScript can "display" data in different ways

Writing into an HTML element, using `innerHTML`.

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>

</body>
</html>
```

Writing into the HTML output using `document.write()`.

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```

Writing into an alert box, using `window.alert()`.

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

Writing into the browser console, using `console.log()`.

```html
<!DOCTYPE html>
<html>
<body>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```

## Single Line Comments

Single line comments start with `//`

```jsx
// comments
```

## Multi-line Comments

Multi-line comments start with `/*` and end with `*/`.

```jsx
/* Hey!
Hello, How are you?
*/ 
```

## Variables

### Declare Variables using

**1. var** -

```javascript
var a = 1; // Declare a variable x with the value 1 (function-level scope).
```

**2. let** -

```javascript
let b = 1; // Declare a variable y with the value 10 (block-level scope).
```

**3. const** -

```javascript
const c = 1; // Declare a read-only variable z with the value 15 (block-level scope).
```

## Data Types

### 1. Primitive Data Types

**numbers** -

```javascript
let number = 10;
```

**strings** -

```javascript
let name = "Manthan";
```

**booleans** -

```javascript
let value1 = true;
let value2 = false;
```

**null** -

```javascript
let value = null;
```

**undefined** -

```javascript
let name;
```

**symbol** -

```javascript
let a = Symbol();
```

### 2. Non Primitive Data Types

**object** -

```javascript
let name = {firstName:"Manthan", lastName:"Ank"};
```

**arrays** -

```javascript
let array = ["value1", "value2"];
```

**regexp** -

Syntax

```javascript
/pattern/modifiers;
```

Example

```javascript
let pattern = /w3schools/i;
```

## Operators

**Arithmetic Operators** -

| Operator | Description |
| ----------- | ----------- |
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| ** | Exponentiation (ES2016) |
| / | Division |
| % | Modulus (Division Remainder) |
| ++ | Increment |
| -- | Decrement |

Examples

```javascript
// Addition
let x = a + b;

// Subtraction
let x = a - b;

// Multiplication
let x = a * b;

// Exponentiation
let x = a ** b;

// Division
let x = a / b;

// Modulus
let x = a % b;

// Increment
let x = a ++ b;

// Decrement
let x = a -- b;
```

**Logical Operators** -

| Operator | Description |
| ----------- | ----------- |
| && | logical and |
| II | logical or |
| ! | logical not |

Examples

```javascript
// Logical AND
let x = (a + b) && (c + d);

// Logical OR
let x = a || b;

// Logical NOT
let x = !a;
```

**Comparison Operators** -

| Operator | Description |
| ----------- | ----------- |
| == | equal to |
| === | equal value and equal type |
| != | not equal |
| !== | not equal value or not equal type |
| > | greater than |
| < | less than |
| >= | greater than or equal to |
| <= | less than or equal to |
| ?| ternary operator |

Examples

```javascript |
let x = 1 == 1
let x = 1 === 1
let x = 1 != 0
let x = 1 !== 0
let x = 1 > 0
let x = 1 < 0
let x = 1 >= 0
let x = 1 <= 0
let x = 1 ? 0
```

**Bitwise Operators** -

| Operator | Description |
| ----------- | ----------- |
| & | AND |
| I | OR |
| ~ | NOT |
| ^| XOR |
| << | Left shift |
| >> | Right shift |
| >>> | Unsigned right |

Examples

```javascript
let x = 1 & 0
let x = 1 | 0
let x = ~1
let x = 1 ^ 0
let x = 1 << 0
let x = 1 >> 0
let x = 1 >>> 0
```

**Type Operators** -

| Operator | Description |
| ----------- | ----------- |
| typeof | Returns the type of a variable |
| instanceof | Returns true if an object is an instance of an object type |

Examples

```javascript
typeof 3 // Returns number
typeof "Manthan" // Returns string
```

**Assignment Operators** -

| Operator | Description |
| ----------- | ----------- |
| = | x = y |
| += | x += y |
| -= | x -= y |
| *= | x *= y |
| /= | x /= y |
| %= | x %= y |
| : | x : 45 |

```javascript
let x = x = y
let x = x += y
let x = x -= y
let x = x *= y
let x = x /= y
let x = x %= y
let x = x : 10
```

**Conditional (Ternary) Operator** -

Syntax

```javascript
(condition) ? x : y
```

**Nullish Coalescing Operator (??)** -

```javascript
let name = null;
let text = "missing";
let result = name ?? text;
```

**Optional Chaining Operator (?.)** -

```javascript
// Create an object:
const car = {type:"Fiat", model:"500", color:"white"};
// Ask for car name:
document.getElementById("demo").innerHTML = car?.name;
```

**delete Operator** -

```javascript
const person = {
  firstName:"Manthan",
  lastName:"Ank",
  age:25,
  eyeColor:"black"
};
delete person.age;
```

**Spread (...) Operator** -

```javascript
const cars1 = ["Saab", "Volvo", ..."BMW"];
const cars2 = ["Fiat", "Toyota"];

const combined = [cars1, ...cars2];
```

## Arrays

```javascript
const letters = ['a', 'b', 'c'];
```

**Array methods** -

concat

```javascript

```

indexOf

```javascript

```

join

```javascript

```

lastIndexOf

```javascript

```

pop

```javascript

```

push

```javascript

```

reverse

```javascript

```

shift

```javascript

```

slice

```javascript

```

sort

```javascript

```

splice

```javascript

```

toString

```javascript

```

unshift

```javascript

```

valueOf

```javascript

```

## Strings

```javascript
const name = 'Manthan';
```

**Strings methods** -

charAt

```javascript

```

charCodeAt

```javascript

```

concat

```javascript

```

fromCharCode

```javascript

```

indexOf

```javascript

```

lastIndexOf

```javascript

```

match

```javascript

```

replace

```javascript

```

search

```javascript

```

slice

```javascript

```

split

```javascript

```

substr

```javascript

```

substring

```javascript

```

toLowerCase

```javascript

```

toUpperCase

```javascript

```

valueOf

```javascript

```

## Loops

for

```javascript

```

while

```javascript

```

do while

```javascript

```

for in

```javascript

```

for of

```javascript

```

## Conditional Statements

if

```javascript

```

if else

```javascript

```

else if

```javascript

```

switch

```javascript

```

## Functions

## Scope

Block Scope

```javascript

```

Function Scope

```javascript

```

Global Scope

```javascript

```

## Dates

```javascript
new Date()
```

### Date Methods

toString

```javascript

```

toDateString

```javascript

```

toUTCString

```javascript

```

toISOString

```javascript

```

## Date Get Methods

getFullYear

```javascript

```

getMonth

```javascript

```

getDate

```javascript

```

getDay

```javascript

```

getHours

```javascript

```

getMinutes

```javascript

```

getSeconds

```javascript

```

getMilliseconds

```javascript

```

getTime

```javascript

```

## Date Set Methods

setDate

```javascript

```

setFullYear

```javascript

```

setHours

```javascript

```

setMilliseconds

```javascript

```

setMinutes

```javascript

```

setSeconds

```javascript

```

setMonth

```javascript

```

setTime

```javascript

```

## Type Conversion

### Covert String to Numbers

Number

```javascript

```

parseFloat

```javascript

```

parseInt

```javascript

```

### Convert Number to a string

toString

```javascript

```

toExponential

```javascript

```

toFixed

```javascript

```

toPrecision

```javascript

```

### Convert Dates to numbers

Number

```javascript

```

getTime

```javascript

```

string

```javascript

```

toString

```javascript

```

### Convert boolean to Number

Number

```javascript

```

### Convert boolean to string

string

```javascript

```

## Arrow Function

```javascript
hello = () => {
    return 'hello';
}
```

## Math

### Math Property

```javascript
Math.property
```

### Math Methods

Math.round

```javascript

```

Math.ceil

```javascript

```

Math.floor

```javascript

```

Math.trunc

```javascript

```

## Sets

### Set Methods

new Set

```javascript

```

add

```javascript

```

delete

```javascript

```

has

```javascript

```

forEach

```javascript

```

values

```javascript

```

## Map

### Map Methods

new Map

```javascript

```

set

```javascript

```

get

```javascript

```

delete

```javascript

```

has

```javascript

```

forEach

```javascript

```

entries

```javascript

```

## Async

Callbacks

```javascript

```

Asynchronous

```javascript

```

Promises

```javascript

```

async/await

```javascript

```

## DOM

Methods

```javascript

```

Documents

```javascript

```

Elements

```javascript

```

HTML

```javascript

```

Forms

```javascript

```

CSS

```javascript

```

Animations

```javascript

```

Events

```javascript

```

Event Listener

```javascript

```

Navigation

```javascript

```

Nodes

```javascript

```

Collections

```javascript

```

Node

```javascript

```

Lists

```javascript

```

## Best Practices

Avoid Global Variables

```javascript

```

Avoid Declare Local Variables

```javascript

```

Declarations on Top

```javascript

```

Intialize Variables

```javascript

```

Declare Objects with const

```javascript

```

Declare Arrays with const

```javascript

```

Don't Use new Objects

```javascript

```

Beware of Automatic Type Conversions

```javascript

```

Use === Comparison

```javascript

```

Use Parameter Defaults

```javascript

```

End Your Switches with Defaults

```javascript

```

Avoid Number, String, and Boolean as Objects

```javascript

```

Avoid Using eval()

```javascript

```

## Common Mistakes

Accidentally Using the Assignment Operator

```javascript

```

Expecting Loose Comparison

```javascript

```

Confusing Addition & Concatenation

```javascript

```

Misundering Floats

```javascript

```

Breaking a JavaScript String

```javascript

```

Misplacing semicolon

```javascript

```

Breaking a Return Statement

```javascript

```

Accessing Arrays with Named Indexes

```javascript

```

Ending Definition with a Comma

```javascript

```

Undefined is Not Null

```javascript

```

## Performance

Reduce Activity in Loops

```javascript

```

Reduce DOM Access

```javascript

```

Reduce DOM Size

```javascript

```

Avoid Unnecessary Variables

```javascript

```

Delay Javascript Loading

```javascript

```

Avoid Using with

```javascript

```

## ES6 Features

The let keyword

```javascript

```

The const keyword

```javascript

```

Arrow Functions

```javascript

```

The ... Operator

```javascript

```

For/of

```javascript

```

Map Objects

```javascript

```

Set Objects

```javascript

```

Classes

```javascript

```

Promises

```javascript

```

Symbol

```javascript

```

Default Parameters

```javascript

```

Function Rest Parameter

```javascript

```

String.includes()

```javascript

```

String.startsWith()

```javascript

```

String.endsWith()

```javascript

```

Array.from()

```javascript

```

Array keys()

```javascript

```

Array find()

```javascript

```

Array findIndex()

```javascript

```

New Math Methods

```javascript

```

New Number Properties

```javascript

```

New Number Methods

```javascript

```

New Global Methods

```javascript

```

Object entries

```javascript

```

JavaScript Modules

```javascript

```

## ES5 Features

"use strict"

```javascript

```

String[number] access

```javascript

```

Multiline strings

```javascript

```

String.trim()

```javascript

```

Array.isArray()

```javascript

```

Array forEach()

```javascript

```

Array map()

```javascript

```

Array filter()

```javascript

```

Array reduce()

```javascript

```

Array reduceRight()

```javascript

```

Array every()

```javascript

```

Array some()

```javascript

```

Array indexOf()

```javascript

```

Array lastIndexOf()

```javascript

```

JSON.parse()

```javascript

```

JSON.stringify()

```javascript

```

Date.now()

```javascript

```

Date toISOString()

```javascript

```

Date toJSON()

```javascript

```

Property getters and setters

```javascript

```

Reserved words as property names

```javascript

```

Object methods

```javascript

```

Object defineProperty()

```javascript

```

Function bind()

```javascript

```

Trailing commas

```javascript

```

## Browser BOM

Window

```javascript

```

Screen

```javascript

```

Location

```javascript

```

History

```javascript

```

Navigator

```javascript

```

Popup Alert

```javascript

```

Timing

```javascript

```

Cookies

```javascript

```

## JSON

Data Types

```javascript

```

Parse

```javascript

```

Stringify

```javascript

```

Objects

```javascript

```

Arrays

```javascript

```

Server

```javascript

```

## Web API

Forms API

```javascript

```

History API

```javascript

```

Storage API

```javascript

```

Worker API

```javascript

```

Fetch API

```javascript

```

GeoLocation API

```javascript

```

## AJAX

XMLHttp

```javascript

```

Request

```javascript

```

Response

```javascript

```

XML File

```javascript

```

## JQuery

Selectors

```javascript

```

## Graphics

Canvas

```javascript

```

Plotly

```javascript

```

Chart.js

```javascript

```

Google Chart

```javascript

```

D3.js

```javascript

```
