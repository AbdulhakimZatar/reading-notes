#  JS Object Literals; The DOM.

## What is the hardest thing about writing code?

1- Learning a new technology.
2- Naming things.
3- Testing your code.
4- Debugging.
5- Fixing bugs.
6- Making software maintainable.

## What is an Object?
Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, variables and functions take on new names.

## Dom
The Document Object Model (DOM) specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.

## The Dom Tree is a Model of a Web Page
As a browser loads a web page, it creates a model of that page. The model is called a DOM tree, and it is stored in the browsers' memory. It consists of four main types of nodes.
![Dom](img/dom.png)

## Working with The Dom Tree
Accessing and updating the DOM tree involves two steps: 
1- Locate the node that represents the element you want to work with. 
2- Use its text content, child elements, and attributes.

## Example of Dom
```
II ADDING ITEMS TO START AND ENO OF LIST
var list = document .getEl ementsByTagName( ' ul ')[OJ; II Get the <u l> el ement
II ADD NEW ITEM TO END OF LIST
var newitemLast = document . createElement('li '); II Create element
var newTextLast = document .createTextNode{'cream'); II Create text node
newitemLast.appendChild(newTextLast);
list.appendChild(newitemLast);
II Add text node to element
II Add element end of list
II ADD NEW ITEM START OF LIST
var newitemFirst = document . createElement('li ') ;
var newTextFirst = document.createTextNode('kale');
newitemFirst.appendChild(newTextFirst);
list.insertBefore(newitemFirst, list.firstChild);
II Create element
II Create text node
II Add text node to element
II Add element to list 
```