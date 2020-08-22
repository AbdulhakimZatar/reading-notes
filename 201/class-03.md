# HTML Lists, CSS Boxes, JS Control Flow

## Lists
There are lots of occasions when we need to use lists. HTML provides us with three different types.

### Types of Lists
1- Ordered lists.
2- Unordered lists.
3- Definition lists.

### Example of Lists
```
<html>
<head>
 <title>Lists</title>
</head>
<body>
 <h1>Scrambled Eggs</h1>
 <p>Eggs are one of my favourite foods. Here is a
 recipe for deliciously rich scrambled eggs.</p>
 <h2>Ingredients</h2>
 <ul>
 <li>2 eggs</li>
 <li>1tbs butter</li>
 <li>2tbs cream</li>
 </ul>
 <h2>Method</h2>
 <ol>
 <li>Melt butter in a frying pan over a medium
 heat</li>
 <li>Gently mix the eggs and cream in a bowl</li>
 <li>Once butter has melted add cream and eggs</li>
 <li>Using a spatula fold the eggs from the edge of
 the pan to the center every 20 seconds (as if
 you are making an omelette)</li>
 <li>When the eggs are still moist remove from the
 heat (it will continue to cook on the plate
 until served)</li>
 </ol>
</body>
</html>
```

![example](imgs/ex_list.png)


## Boxes
At the beginning of this section on CSS, you saw how CSS treats each HTML element as if it lives in its own box.

### How to Control Box Dimensions?
By default a box is sized just big enough to hold its contents. To set your own dimensions for a box you can use the height and width properties.

### Border, Margin & Padding
Every box has three available properties that can be adjusted to control its appearance:
1- Border.
2- Margin.
3- Padding.

## Switch Statement
A switch statement starts with a variable called the switch value. Each case indicates a possible value for this variable and the code that should run if the variable matches that value.
Switch statements allow you to compare a value against possible outcomes (and also provides a default option if none match).

### Example of Switch
```
switch (level) {
case 'One ':
title= 'Level 1 ' ;
break;
case 'Two':
tit 1 e = ' Level 2 ' ;
break;
case ' Three' :
title = 'Level 3' ;
break ;
default :
title= 'Test';
break; 
}
```
