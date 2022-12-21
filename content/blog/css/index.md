---
title: CSS
date: "2022-12-21"
description: "Complete CSS Guide"
tags: ["css"]
---

**CSS** - Stands for Cascading Style Sheets

CSS describes how HTML elements are to be displayed on screen, paper, or in other media
CSS saves a lot of work. It can control the layout of multiple web pages all at once
External stylesheets are stored in CSS files.

## CSS Syntax

```css
h1 {
    color: #000000;
}
/* Where h1 is selector, color is property, and #000000 is value. Both with property and value are declaration. */
```

## Seectors

Used to "find" (or select) the HTML elements you want to style.

### CSS Selectors are divided into five categories `:`

**Simple selectors** - select elements based on name, id, class

**Combinator selectors** - select elements based on a specific relationship between them

**Pseudo-class selectors** - select elements based on a certain state

**Pseudo-elements selectors** - select and style a part of an element

**Attribute selectors** - select elements based on an attribute or attribute value

Here are most basic CSS selectors used `:`

**1. CSS element Selector** - selects HTML elements based on the element name.

```css
p {
  text-align: center;
  color: blue;
}
```

**2. CSS id Selector** - uses the id attribute of an HTML element to select a specific element.

To select an element with a specific id, write a hash (#) character, followed by the id of the element.

```css
#para1 {
  text-align: center;
  color: blue;
}
```

**3. CSS class Selector** - selects HTML elements with a specific class attribute.

To select elements with a specific class, write a period (.) character, followed by the class name.

```css
.center {
  text-align: center;
  color: blue;
}
```

You can also specify that only specific HTML elements should be affected by a class.

```css
p.center {
  text-align: center;
  color: blue;
}
```

HTML elements can also refer to more than one class.

```css
<p class="center large">This paragraph refers to two classes.</p>
```

**4. CSS Universal Selector** - selects all HTML elements on the page.

```css
* {
  text-align: center;
  color: blue;
}
```

**5. CSS Grouping Selector** - selects all the HTML elements with the same style definitions.

```css
h1, h2, p {
  text-align: center;
  color: blue;
}
```
