---
title: HTML
date: "2022-11-28"
description: "Complete HTML Guide"
tags: ["html"]
---

**HTML** - Stands for Hyper Text Markup Language

**`<!DOCTYPE>` Declaration** - Represents the document type and helps browsers to display web pages correctly.

## Elements

An HTML element is defined by a start tag, some content, and an end tag.

```html
<tagname>Content goes here...</tagname>
```

## Attributes

**href** - defines a hyper link.

```html
<a href="https://www.w3schools.com">Visit W3Schools</a>
```

**src** - used to embed images in the web pages.

```html
<img src="img.jpg">
```

- Absolute URL - Links to an external image that is hosted on another website.

```html
<img src="https://www.w3schools.com/images/img.jpg">
```

- Relative URL - Links to an image that is hosted within the website.

```html
<img src="/images/img.jpg">
```

**width & height** - specify the width and height of the image (in pixels).

```html
<img src="img.jpg" width="300" height="300">
```

**alt** - specifies an alternate text for an image, if the image for some reason cannot be displayed.

```html
<img src="img.jpg" alt="Image of a jacket">
```

**style** - used to add styles to an element, such as color, font, size, and more.

```html
<p style="color:red;">This is a red paragraph.</p>
```

**lang** - used to declare the language of the Web page. And always included inside the `<html>` tag.

```html
<html lang="en">
```

**title** - defines some extra information about an element.

```html
<p title="I'm a tooltip">This is a paragraph.</p>
```
