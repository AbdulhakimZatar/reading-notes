# Basics of HTML, CSS & JS

## Text
When creating a web page, you add tags (known as markup) to the contents of the page. 
These tags provide extra meaning and allow browsers to show users the appropriate structure for the page.

### Visual Editors & Their Code views
Content management systems and HTML editors such as Dreamweaver usually have two views of the page you are creating: a visual editor and a code view.

### Semantic Markup
There are some text elements that are not intended to affect the structure of your web pages, but they do add extra information to the pages — they are known as semantic markup.

### Example on text
```
<html>
<head>
 <title>Text</title>
</head>
<body>
 <h1>The Story in the Book</h1>
 <h2>Chapter 1</h2>
 <p>Molly had been staring out of her window for about
 an hour now. On her desk, lying between the copies
 of <i>Nature</i>, <i>New Scientist</i>, and all
 the other scientific journals her work had
 appeared in, was a well thumbed copy of <cite>On
 The Road</cite>. It had been Molly's favorite book
 since college, and the longer she spent in these
 four walls the more she felt she needed to be
 free.</p>
 <p>She had spent the last ten years in this room,
 sitting under a poster with an Oscar Wilde quote
 proclaiming that <q>Work is the refuge of
 people who have nothing better to do</q>. Although
 many considered her pioneering work, unraveling
 the secrets of the llama <abbr
 title="Deoxyribonucleic acid">DNA</abbr>, to be an
 outstanding achievement, Molly <em>did</em> think
 she had something better to do.</p>
</body>
</html>
```

## Introducing CSS
CSS allows you to create rules that specify how the content of an element should appear. For example, you can specify that the background of the page is cream, all paragraphs should appear in gray using the Arial typeface, or that all level one headings should be in a blue, italic, Times typeface.
CSS properties affect how elements are displayed.

### Understanding CSS
The key to understanding how CSS works is to imagine that there is an invisible box around every HTML element.

### Example on CSS
```
<!DOCTYPE html>
<html>
<head>
 <title>Introducing CSS</title>
 <link href="css/example.css" type="text/css"
 rel="stylesheet" />
</head>
<body>
 <h1>From Garden to Plate</h1>
 <p>A <i>potager</i> is a French term for an
 ornamental vegetable or kitchen garden ... </p>
 <h2>What to Plant</h2>
 <p>Plants are chosen as much for their functionality
 as for their color and form ... </p>
</body>
</html>
body {
font-family: Arial, Verdana, sans-serif;}
h1, h2 {
color: #ee3e80;}
p {
color: #665544;}
```

### Why use External Style Sheets?
When building a website there are several advantages to placing your CSS rules in a separate style sheet.
Sometimes you might consider placing CSS rules in the same page as your HTML code.

## Basic JavaScript Instructions
A script is a series of instructions that a computer can follow one-by-one. Each individual instruction or step is known as a statement. Statements should end with a semicolon.

### What is a Varriable?
A script will have to temporarily store the bits of information it needs to do its job. It can store this data in variables.
A variable is a good name for this concept because the data stored in a variable can change (or vary) each time a script runs.

### Data Types
JavaScript distinguishes between numbers, strings, and true or false values known as Booleans.
* Numeric data type
* String data type
* Booleandata type

### Example on Javascript
```
II Create variables for the welcome message
var greeting = 'Howdy ';
var name = 'Molly';
var message= ', please check your order: ' ;
c02/ js/example.js
II Concatenate the three variables above to creat e t he welcome message
var welcome = greeting + name + message;
II Create variables to hold details about the sign
var sign = 'Montague House' ;
var tiles= sign.length;
var subTotal = tiles * 5;
var shipping = 7;
var grandTotal = subTotal + shipping;
II Get the element that has an id of greeti ng
var el = document .getElementByid('greeting') ;
II Replace the content of that element with the personal ized welcome message
el .textContent = welcome;
II Get the el ement that has an id of userSign then update its contents
var el Sign = document .getElementByld('userSign '))
elSign .textContent = sign ;
II Get the element that has an id of ti l es then update its contents
var elTiles = document .getElementByid('tiles');
elTiles.textContent = tiles;
II Get the element that has an id of subTotal then update its contents
var elSubTotal = document.getElementByid('subTotal ');
el SubTotal .textContent = ' $' + subTotal;
II Get the element that has an id of shipping then update its contents
var elSubTotal = document .getElementByid('shipping') ;
elSubTotal .textContent = '$' +shipping;
II Get the element that has an id of grandTotal then update its contents
var elGrandTotal = document.getElementByid( 'grandTotal ') ;
elGrandTotal .textContent = '$ ' + grandTotal; 
```

### Arrays
An array is a special type of variable. It doesn't just store one value; it stores a list of values.

### Values in Arrays
Values in an array are accessed as if they are in a numbered list. It is important to know that the numbering of this list starts at zero.


### Example on Arrays
```
// Create the array
var colors = ['white',
'black' ,
'custom'];
// Update the third item in the array
colors[2] = 'beige ' ;
// Get the element with an id of col ors
var el = document .getElementByid(' colors') ;
// Replace with third item from the array
el .textContent = colors[2]; 
```

## Decisions and Loops
The code can take more than one path, which means the browser runs different code in different situations. In this chapter, you will learn how to create and control the flow of data in your scripts to handle different situations.

## Loops
Loops check a condition if it return true, a code will run, then it will be checked again until it returns false.

### Types of loops
* For.
* While.
* Do While.

### Loops Counters
* Initialization.
var i = 0;
* Condition
i < 10;
* Update
i++

### Using for Loops
```
var scores= [24. 32, 17]; //Array of scores
var arraylength scores.l ength; // Items in array
var roundNumber = O; //Current round
var msg ''; //Message
var i ; // Counter
//Loop through the items in the array
for (i = O; i < arraylength; i++) {
//Arrays are zero based (so 0 is round 1)
//Add 1 to the current round
roundNumber = (i + l);
// Write the current round to message
msg += 'Round ' + roundNumber + ' : ';
//Get the score from the scores array
msg += scores[i] + '<br / >' ;
document .getElementByid( 'answer') .i nnerHTML msg; 
```

### Using while Loops
```
var i = l ;
var msg = ' ' ;
II Set counter to 1
II Message
II Store 5 times tabl e in a variable
while (i < 10) {
msg += i + ' x 5 = ' + (i * 5) + '<br I>';
i++;
document .getEl ementByid( ' answer') . innerHTML = msg; 
```

### Using do while Loops
```
var i = l;
var msg : I I •
•
II Set counter to 1
II Message
II Store 5 times table in a variable
do {
msg += i + ' x 5 = ' + (i * 5) + '<br I>' ;s
i++;
} wh il e ( i < 1) ;
II Note how this is already 1 and it still runs
document .getEl ementByld(' answer').innerHTML = msg; 
```