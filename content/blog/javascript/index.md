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

```

**Logical Operators** -

| Operator | Description |
| ----------- | ----------- |
| && | logical and |
| II | logical or |
| ! | logical not |

Examples

```javascript

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

```javascript |

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

```

**Type Operators** -

| Operator | Description |
| ----------- | ----------- |
| typeof | Returns the type of a variable |
| instanceof | Returns true if an object is an instance of an object type |
Examples

```javascript

```

## Arrays

```javascript
const letters = ['a', 'b', 'c'];
```

**Array methods** -

concat

indexOf

join

lastIndexOf

pop

push

reverse

shift

slice

sort

splice

toString

unshift

valueOf

## Strings

```javascript
const name = 'Manthan';
```

**Strings methods** -

charAt

charCodeAt

concat

fromCharCode

indexOf

lastIndexOf

match

replace

search

slice

split

substr

substring

toLowerCase

toUpperCase

valueOf

## Loops

for

while

do while

for in

for of

## Conditional Statements

if

else

else if

switch

## Functions

## Scope

Block Scope

Function Scope

Global Scope

## Dates

```javascript
new Date()
```

### Date Methods

toString

toDateString

toUTCString

toISOString

## Date Get Methods

getFullYear

getMonth

getDate

getDay

getHours

getMinutes

getSeconds

getMilliseconds

getTime

## Date Set Methods

setDate

setFullYear

setHours

setMilliseconds

setMinutes

setSeconds

setMonth

setTime

## Type Conversion

### Covert String to Numbers

Number

parseFloat

parseInt

### Convert Number to a string

toString

toExponential

toFixed

toPrecision

### Convert Dates to numbers

Number

getTime

string

toString

### Convert boolean to Number

Number

### Convert boolean to string

string

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

Math.ceil

Math.floor

Math.trunc

## Sets

### Set Methods

new Set

add

delete

has

forEach

values

## Map

### Map Methods

new Map

set

get

delete

has

forEach

entries

## Async

Callbacks

Asynchronous

Promises

async/await

## DOM

Methods

Documents

Elements

HTML

Forms

CSS

Animations

Events

Event Listener

Navigation

Nodes

Collections

Node

Lists

## Best Practices

Avoid Global Variables

Avoid Declare Local Variables

Declarations on Top

Intialize Variables

Declare Objects with const

Declare Arrays with const

Don't Use new Objects

Beware of Automatic Type Conversions

Use === Comparison

Use Parameter Defaults

End Your Switches with Defaults

Avoid Number, String, and Boolean as Objects

Avoid Using eval()

## Common Mistakes

Accidentally Using the Assignment Operator

Expecting Loose Comparison

Confusing Addition & Concatenation

Misundering Floats

Breaking a JavaScript String

Misplacing semicolon

Breaking a Return Statement

Accessing Arrays with Named Indexes

Ending Definition with a Comma

Undefined is Not Null

## Performance

Reduce Activity in Loops

Reduce DOM Access

Reduce DOM Size

Avoid Unnecessary Variables

Delay Javascript Loading

Avoid Using with

## ES6 Features

The let keyword

The const keyword

Arrow Functions

The ... Operator

For/of

Map Objects

Set Objects

Classes

Promises

Symbol

Default Parameters

Function Rest Parameter

String.includes()

String.startsWith()

String.endsWith()

Array.from()

Array keys()

Array find()

Array findIndex()

New Math Methods

New Number Properties

New Number Methods

New Global Methods

Object entries

JavaScript Modules

## ES5 Features

"use strict"

String[number] access

Multiline strings

String.trim()

Array.isArray()

Array forEach()

Array map()

Array filter()

Array reduce()

Array reduceRight()

Array every()

Array some()

Array indexOf()

Array lastIndexOf()

JSON.parse()

JSON.stringify()

Date.now()

Date toISOString()

Date toJSON()

Property getters and setters

Reserved words as property names

Object methods

Object defineProperty()

Function bind()

Trailing commas

## Browser BOM

Window

Screen

Location

History

Navigator

Popup Alert

Timing

Cookies

## JSON

Data Types

Parse

Stringify

Objects

Arrays

Server

## Web API

Forms API

History API

Storage API

Worker API

Fetch API

GeoLocation API

## AJAX

XMLHttp

Request

Response

XML File

## JQuery

Selectors

## Graphics

Canvas

Plotly

Chart.js

Google Chart

D3.js
