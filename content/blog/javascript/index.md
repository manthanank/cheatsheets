---
title: JavaScript
date: "2022-12-23"
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

**Array methods** -

## Strings

**Strings methods** -

## Loops

## Functions
