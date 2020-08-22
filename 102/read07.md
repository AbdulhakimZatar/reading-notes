# JavaScript


## Intro + Scripts

### How JavaScript makes website more interactive?
* Access content.
* Modify content.
* Program rules.
* React to events.

### Examples of JavaScript
1- Slideshow.
2- Forms.
3- Reload part of page.
4- Filtering data.

### What is a Script?
A script is a series of instructions that a computer can follow to achieve a goal.

### Sketching Tasks in a Flowchart
Often scripts will need to perform different tasks in different situations.
You can use flowcharts to work out how the tasks fit together.
The flowcharts show the paths between each step. 

![sketch](img/read07)



## Expressions + Operators

### Expressions
An expression evaluates into a single value. Broadly speaking
there are two types of expressions.

### Type of Expressions
1- Expressions that just assign a value to a variable.
2- Expressions that use two or more values to return a single value

### Operators
Expressions rely on things called operators; they allow programmers to
create a single value from one or more values.

### Arithmetic Operators
JavaScript contains the following mathematical operators, which you can use with numbers.
You may remember some from math class. 

Name | Operator 
--- | ---
Addition | +
Subtraction | -
Division | /
Multiplaction | *
Increment | ++
Decrement | --


```
var subtotal (13 + 1) * 5; II Subtotal is 70
var shipping 0.5 * (13 + 1) ; II Shipping is 7
var total subtotal + shipping ; II Total is 77
var el Sub document .getElementByid(' subtotal ') ;
elSub .textContent =subtotal ;
var elShip = document .getElement Byid('shi ppi ng ') ;
elShip.textContent =shipping;
var elTotal = document .getElementByid('total ');
elTotal .textContent =total; 
```

### String Operator
There is just one string operator: the+ symbol.
It is used to join the strings on either side of it. 

```
var greeting= 'Howdy ';
var name= 'Mol ly' ;
var welcomeMessage = greeting+ name+ '!';
var el = document.getElementByld('greeting');
el .textContent = welcomeMessage; 
```


## Functions

### What is Function
Functions let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can reuse the function 

### Example of a Basic Function
html
```
<!DOCTYPE html>
<html>
<head>
<title>Basic Function</title>
<link rel ="stylesheet" href="css/ c03.css" />
</head>
<body>
<hl>TravelWorthy</ hl>
<div id="message">We lcome to our site! </ div>
<script src="js/ basic-function .js"></script>
</body>
</html> 
```

JavaScript
```
var msg = 'Sign up to receive our newsletter for 10% off!';
function updateMessage() {
var el = document.getElementByld('message'};
el .textContent = msg;
}
updateMessage(}; 
```

![result](img/ex_result.png)