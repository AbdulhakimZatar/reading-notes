# HTML Tables; JS Constructor Functions

## Domain Modeling
Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domain model that's articulated well can verify and validate the understanding of a specific problem among various stakeholders. As a communication tool, it defines a vocabulary that can be used within and between both technical and business teams.

Here's some tips to follow when building your own domain models.

1- When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
2- Model its attributes with a constructor function that defines and initializes properties.
3- Model its behaviors with small methods that focus on doing one job well.
4- Create instances using the new keyword followed by a call to a constructor function.
5- Store the newly created object in a variable so you can access its properties and methods from outside.
6- Use the this variable within methods so you can access the object's properties and methods from inside.

## Tables
A table represents information in a grid format. Examples of tables include financial reports, TV schedules, and sports results.

### Example of Tables
```
<html>
<head>
 <title>Tables</title>
</head>
<body>
 <table>
 <thead>
 <tr>
 <th></th>
 <th scope="col">Home starter hosting</th>
 <th scope="col">Premium business hosting</th>
 </tr>
 </thead>
 <tbody>
 <tr>
 <th scope="row">Disk space</th>
 <td>250mb</td>
 <td>1gb</td>
 </tr>
 <tr>
 <th scope="row">Bandwidth</th>
 <td>5gb per month</td>
 <td>50gb per month</td>
 </tr>
 <!-- more rows like the two above here -->
 </tbody>
 <tfoot>
 <tr>
 <td></td>
 <td colspan="2">Sign up now and save 10%!</td>
 </tr>
 </tfoot>
 </table>
</body>
</html>
```

## Functions, Methods, and Objects

### Creating an Object
The keyword and the object constructor craete a blank object.
You can then add properites and methods to the object.

### THIS
The keyword this is commonly used inside functions and objects. Where the function is declared alters what this means. It always refers to one object, usually the object in which the function operates.

### Data Types Revisited
In JavaScript there are six data types: Five of them are described as simple (or primitive) data types. The sixth is the object (and is referred to as a complex data type).

1- String.
2- Number.
3- Boolean.
4- Undefined.
5- Null.
6- Object.
