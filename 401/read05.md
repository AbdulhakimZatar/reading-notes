# Linked Lists

## What is a Linked List
A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

### Types of Linked List 
Singly and Doubly.


## Terminology
Linked List - A data structure that contains nodes that links/points to the next node in the list.
Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
Next - Each node contains a property called Next. This property contains the reference to the next node.
Head - The Head is a reference type of type Node to the first node in a linked list.
Current - The Current reference is a reference type of type Node that is currently being looked at. This node is traditionally used when traversing through a full linked list. When traversing, you typically reset the current to the head to guarantee you are starting from the beginning of the linked list.


## Basics of linked lists
If we really want to understand the basics of linked lists, it’s important that we talk about what type of data structure they are.
One characteristic of linked lists is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed. 

## Memory management
The biggest differentiator between arrays and linked lists is the way that they use memory in our machines. Those of us who work with dynamically typed languages like Ruby, JavaScript, or Python don’t have to think about how much memory an array uses when we write our code on a day to day basis because there are several layers of abstraction that end up with us not having to worry about memory allocation at all.
![ex](https://miro.medium.com/max/700/1*G43FVT5xJ1n1QDKVNZUxXQ.jpeg)

## What does it look like
![ex](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList1.PNG)

### Traversal
When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing.




## Prerequisites
1- When making your Node class, consider requiring a value to be passed in to require that each node has a value.

2- When making a Linked List, you may want to require that at least one node gets passed in upon instantiation. This first node is what your Head and Current will point too.

