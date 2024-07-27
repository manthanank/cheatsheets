---
title: Expressjs Cheatsheet
date: "2022-12-21"
description: "Complete Express.js Guide."
---

## Setup

```jsx
mkdir app-name
cd myapp
```

```jsx
npm init

entry point: (index.js)

npm install express

npm install express --no-save
```

In index.js

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

Run app

```jsx
node app.js
```

## **Express application generator**

```jsx
npx express-generator

or 

npm install -g express-generator
express
```

```bash
cd myapp
npm install
```

## **Basic routing**

`app.METHOD(PATH, HANDLER)`

The following examples illustrate defining simple routes.

Respond with `Hello World!` on the homepage:

```js
app.get('/', (req, res) => {
  res.send('Hello World!')
})
```

Respond to POST request on the root route (`/`), the application’s home page:

```js
app.post('/', (req, res) => {
  res.send('Got a POST request')
})
```

Respond to a PUT request to the `/user` route:

```js
app.put('/user', (req, res) => {
  res.send('Got a PUT request at /user')
})
```

Respond to a DELETE request to the `/user` route:

```js
app.delete('/user', (req, res) => {
  res.send('Got a DELETE request at /user')
})
```

## **Serving static files in Express**

`express.static(root, [options])`

```jsx
app.use(express.static('public'))

// To use multiple static assets directories, call the express.static middleware function multiple times:

app.use(express.static('public'))
app.use(express.static('files'))
```

```jsx
app.use('/static', express.static('public'))
```

```jsx
const path = require('path')
app.use('/static', express.static(path.join(__dirname, 'public')))
```

### Examples -

[express/examples at master · expressjs/express](https://github.com/expressjs/express/tree/master/examples)
