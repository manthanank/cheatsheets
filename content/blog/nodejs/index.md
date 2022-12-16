---
title: Node.js
date: "2022-11-28"
description: "Complete Node.js Guide."
tags: ["nodejs"]
---

Example :

```jsx
const http = require('http')

const hostname = '127.0.0.1'
const port = 3000

const server = http.createServer((req, res) => {
  res.statusCode = 200
  res.setHeader('Content-Type', 'text/plain')
  res.end('Hello World\n')
})

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`)
})
```

Install :

```jsx
npm i
```

Installing package :

```jsx
npm install <package-name>
```

Installing Specific version :

```jsx
npm install <package-name>@<version>
```

Update :

```jsx
npm update
```

Updating package :

```jsx
npm update <package-name>
```

Running :

```jsx
npm run watch
npm run dev
npm run prod
```

Restart the application automatically

```jsx
npm i -g nodemon
```

```jsx
npm i --save-dev nodemon
```

Run the application using the `nodemon`command followed by the application's file name:

```jsx
nodemon app.js
```

Using REPL

```jsx
node
```