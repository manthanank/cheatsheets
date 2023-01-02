---
title: JavaScript
date: "2022-12-30"
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

**var** -

**let** -

**const** -

## Data Types

### 1. Primitive Data Types

**numbers** -

**strings** -

**booleans** -

**null** -

**undefined** -

**symbol** -

Examples :

```jsx
//numbers
let number = 10;

//strings
let name = "Manthan";

//boolean
let value = true/false;

//null
let value = null;

//undefined
let name;

//symbol
let a = Symbol();

```

### 2. Non Primitive Data Types

**objects** -

**arrays** -

**regexp** -

Example :

```jsx
//object
let name = {firstName:"Manthan", lastName:"Ank"};

//array
let array = ["value1", "value2"]

//regExp
let pattern = /w3schools/i;
```

## Operators

**Basic Operators** -

**Logical Operators** -

**Comparison Operators** -

**Bitwise Operators** -

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
