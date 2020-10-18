# Express

## Review, Research, and Discussion

**What’s the difference between PUT and PATCH?**
* PUT: Making a PUT request can lead to a number of outcomes.
* PATCH: is used when you want to apply a partial update to the resource.

**Provide links to 3 services or tools that allow you to “mock” an API for development like json-server**
* Postman
* Swagger
* httpie

**Compare and contrast SOAP and ReST**
* SOAP stands for Simple Object Access Protocol whereas REST stands for Representational State Transfer.
* SOAP is a protocol whereas REST is an architectural pattern.
* SOAP uses service interfaces to expose its functionality to client applications while REST uses Uniform Service locators to access to the components on the hardware device.
* SOAP needs more bandwidth for its usage whereas REST doesn’t need much bandwidth.
* SOAP only works with XML formats whereas REST work with plain text, XML, HTML and JSON.
* SOAP cannot make use of REST whereas REST can make use of SOAP.

## Document the following Vocabulary Terms
* **SOAP**: is a protocol which was designed before REST and came into the picture. The main idea behind designing SOAP was to ensure that programs built on different platforms and programming languages could exchange data in an easy manner. SOAP stands for Simple Object Access Protocol.
* **ReST Verbs**: specify an action to be performed on a specific resource or a collection of resources.
* **CRUD Verbs**: major portion of our “uniform interface” constraint and provide us the action counterpart to the noun-based resource. 
* **Swagger**: Swagger is in essence an Interface Description Language for describing RESTful APIs expressed using JSON. 

## Preparation Materials

### Using middleware
Express is a routing and middleware web framework that has minimal functionality of its own: An Express application is essentially a series of middleware function calls.

Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.

Middleware functions can perform the following tasks:
* Execute any code.
* Make changes to the request and the response objects.
* End the request-response cycle.
* Call the next middleware function in the stack.

#### Application-level middleware
This example shows a middleware function with no mount path. The function is executed every time the app receives a request.

```js
var express = require('express')
var app = express()

app.use(function (req, res, next) {
  console.log('Time:', Date.now())
  next()
})
```
![ex](https://www.tutorialspoint.com/expressjs/images/middleware_desc.jpg)