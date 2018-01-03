## Introduction to Express

### Workshop Topics

---

## Building a basic NodeJS server application

---

@title[Express App]

```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => res.send('Hello World!'));

app.listen(3000, () => {
    console.log('Example app listening on port 3000!'));
};
```

---

## Routing Requests

Routing refers to determining how an application responds to a
client request to a particular endpoint.

---

@title[Routing Requests]

```javascript
app.get('/', (req, res) => {
  res.send('Hello World!')
});
```

```javascript
app.delete('/user', (req, res) => {
  res.send('Got a DELETE request at /user')
});
```

---

## Middleware

Middleware are functions that can enhance or modify a request, add security, or preemptively render a response. 
We'll write basic middleware function in today's workshop.

---

- Here is a simple example of a middleware function called “myLogger”. This function just prints “LOGGED” when
a request to the app passes through it. The middleware function is assigned to a variable named myLogger.

```javascript
const myLogger = (req, res, next) => {
  console.log('LOGGED')
  next()
};

app.use(myLogger);
```

---

## Express MVC Pattern

Introduction to creating a model and rendering a view with Express and Pug

---

### Set view engine

```javascript
app.set('view engine', 'pug');
```

### index.pug template

```pug
doctype html
html
  head
    title= title
  body
    h1= message
```

#### Model & View

```javascript
app.get('/', (req, res) => {
  res.render('index', { title: 'Hey', message: 'Hello there!' })
});
```

