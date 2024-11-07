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

## **Middleware**

Middleware functions are functions that have access to the request object (`req`), the response object (`res`), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named `next`.

### Example of a simple middleware function

```js
const express = require('express')
const app = express()

const myLogger = (req, res, next) => {
  console.log('LOGGED')
  next()
}

app.use(myLogger)

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(3000, () => {
  console.log('Example app listening on port 3000')
})
```

## **Error Handling**

Error-handling middleware functions are defined in the same way as other middleware functions, except they have four arguments instead of three: (err, req, res, next).

### Example of an error-handling middleware function

```js
const express = require('express')
const app = express()

app.get('/', (req, res) => {
  throw new Error('BROKEN') // Express will catch this on its own.
})

app.use((err, req, res, next) => {
  console.error(err.stack)
  res.status(500).send('Something broke!')
})

app.listen(3000, () => {
  console.log('Example app listening on port 3000')
})
```

## **Using Template Engines**

Express supports many template engines. Below is an example of using Pug as the template engine.

### Example of setting up Pug

```js
const express = require('express')
const app = express()

app.set('view engine', 'pug')

app.get('/', (req, res) => {
  res.render('index', { title: 'Hey', message: 'Hello there!' })
})

app.listen(3000, () => {
  console.log('Example app listening on port 3000')
})
```

## **Handling Forms**

Express can handle form submissions using the `body-parser` middleware.

### Example of handling form data

```js
const express = require('express')
const bodyParser = require('body-parser')
const app = express()

app.use(bodyParser.urlencoded({ extended: false }))

app.post('/submit-form', (req, res) => {
  res.send(`Hello ${req.body.name}`)
})

app.listen(3000, () => {
  console.log('Example app listening on port 3000')
})
```

## **Database Integration**

Express can be integrated with databases like MongoDB using libraries like Mongoose.

### Example of connecting to MongoDB with Mongoose

```js
const express = require('express')
const mongoose = require('mongoose')
const app = express()

mongoose.connect('mongodb://localhost/test', { useNewUrlParser: true, useUnifiedTopology: true })

const Cat = mongoose.model('Cat', { name: String })

app.get('/add-cat', (req, res) => {
  const kitty = new Cat({ name: 'Zildjian' })
  kitty.save().then(() => res.send('Cat added!'))
})

app.listen(3000, () => {
  console.log('Example app listening on port 3000')
})
```
