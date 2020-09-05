# EJS
 EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. No religiousness about how to organize things. No reinvention of iteration and control-flow. It's just plain JavaScript.


## Features
1- Fast compilation and rendering

2- Simple template tags: <% %>

3- Custom delimiters (e.g., use [? ?] instead of <% %>)

4- Sub-template includes

5- Both server JS and browser support

6- Complies with the Express view system

7- Static caching of templates

8- Static caching of intermediate JavaScript

9- Ships with CLI

### Get Started

**Install**
```
$ npm install ejs
```

**Use**
```
let ejs = require('ejs');
let people = ['geddy', 'neil', 'alex'];
let html = ejs.render('<%= people.join(", "); %>', {people: people});
```

**Browser support**
```html
<script src="ejs.js"></script>
<script>
  let people = ['geddy', 'neil', 'alex'];
  let html = ejs.render('<%= people.join(", "); %>', {people: people});
</script>
```