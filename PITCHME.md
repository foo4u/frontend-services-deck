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

Here is a simple example of a middleware function called “myLogger”. This function just prints “LOGGED” when
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

```javascript
app.set('view engine', 'pug');
```

```pug
doctype html
html
  head
    title= title
  body
    h1= message
```

```javascript
app.get('/', (req, res) => {
  res.render('index', { title: 'Hey', message: 'Hello there!' })
});
```



## Template Help

- [Code Presenting](https://github.com/gitpitch/gitpitch/wiki/Code-Presenting)
  + [Repo Source](https://github.com/gitpitch/gitpitch/wiki/Code-Delimiter-Slides), [Static Blocks](https://github.com/gitpitch/gitpitch/wiki/Code-Slides), [GIST](https://github.com/gitpitch/gitpitch/wiki/GIST-Slides) 
- [Custom CSS Styling](https://github.com/gitpitch/gitpitch/wiki/Slideshow-Custom-CSS)
- [Slideshow Background Image](https://github.com/gitpitch/gitpitch/wiki/Background-Setting)
- [Slide-specific Background Images](https://github.com/gitpitch/gitpitch/wiki/Image-Slides#background)
- [Custom Logo](https://github.com/gitpitch/gitpitch/wiki/Logo-Setting) [TOC](https://github.com/gitpitch/gitpitch/wiki/Table-of-Contents) [Footnotes](https://github.com/gitpitch/gitpitch/wiki/Footnote-Setting)

---

### Template Versions

- #### [Base Template  @fa[external-link gp-download]](https://gitpitch.com/gitpitch/templates/white)
- #### [Code Maximized @fa[external-link gp-download]](https://gitpitch.com/gitpitch/templates/white?p=codemax)
- #### [Speaker Notes @fa[external-link gp-download]](https://gitpitch.com/gitpitch/templates/white?p=speaker)

---

### Questions?

<br>

@fa[twitter gp-contact](@gitpitch)

@fa[github gp-contact](gitpitch)

@fa[medium gp-contact](@gitpitch)

---?image=assets/image/gitpitch-audience.jpg&opacity=100

@title[Download this Template!]

### <span class="white">Get your presentation started!</span>
### [Download this template @fa[external-link gp-download]](https://gitpitch.com/template/download/white)

