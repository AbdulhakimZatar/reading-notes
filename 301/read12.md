# EJS Partials
Used to help us to avoid repetition of the same code on several web pages.

For example, you may want the same header for several web pages.
EJS partials work like EJS layouts too in creating a single fix content on a web page.

### Example
Let's see an example for,
Open your text editor and type the following code, save as app.js.

```js
var express = require('express');
var ejs = require('ejs');
var app = express();
app.set('view engine', 'ejs');
app.get("/", function(req, res) {
    res.render("home");
});
app.get("/about", function(req, res) {
    res.render("about");
});
app.listen(3000, function() {
    console.log("server is listening!!!");
});
```

We created 2 routes and have rendered both routes to an ejs file.
Now let's create our ejs files.

Open a text editor and type the following code, save as home.ejs
```js
<%- include('partials/partial') %>
    <h4> Home Page</h4>
```

The home.ejs file has a link to the partial.ejs file which serves as the partial.
Open a text editor and type the following code, save as about.ejs
```js
<h3> About US</h3>
```

1. You can clearly see that the about.ejs file has no link to the partial so it won't display the partial.

2. Take a look at the different ejs tag used here.

3. The logic here is, the server which is the app.js file is linked to the home.ejs and about.ejs files which the home.ejs file is linked to the partial with file name partial.ejs.

```js
 <%- include('partials/partial') %>
 ```

1. The path indicates that the partial is located in the partials folder. Partials folder is found in the views folder which is the default template engine location for express.

2. Take Note: The folder name views is not a random word I selected but it's the reserved folder name where express checks for template engine by default.

3. Finally, initiate the app.js file with node app.js in a terminal and view the port in a browser.

### Output
![ex](https://www.includehelp.com/node-js/Images/ejs-partials-1.jpg)
![ex](https://www.includehelp.com/node-js/Images/ejs-partials-2.jpg)