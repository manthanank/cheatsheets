---
title: Node.js with dotenv
date: "2023-01-04"
description: "Node.js with dotenv."
tags: ["nodejs"]
---

Install :

```jsx
npm i dotenv
```

Usage :

Create .env file

```jsx
PORT = 3000
KEY = "values"
```

Import and configure dotenv:

```jsx
require('dotenv').config()
// console.log(process.env.PORT)
```

Examples :

[https://github.com/dotenv-org/examples](https://github.com/dotenv-org/examples)