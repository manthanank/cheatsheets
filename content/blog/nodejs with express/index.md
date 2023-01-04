---
title: Node.js with Express.js
date: "2023-01-04"
description: "Node.js with Express.js."
tags: ["nodejs"]
---

Installation

```bash
npm init

or

npm init -y
npm init --yes
```

Install express

```bash
npm install express
```

Example :

```jsx
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```

Save as index.js (filename.js)

Run the application using the `node`command followed by the application's file name:

```bash
node index.js
```

Stackblitz Link :

[https://stackblitz.com/edit/node-nzw4cm?file=index.js](https://stackblitz.com/edit/node-nzw4cm?file=index.js)