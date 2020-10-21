# Stacks and Queues

## What is a Stack
A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.

Stacks follow these concepts:
* **FILO**:
First In Last Out

This means that the first item added in the stack will be the last item popped out of the stack.

* **LIFO**:Last In First Out

This means that the last item added to the stack will be the first item popped out of the stack.

### Stack Visualization
Here’s an example of what a stack looks like. As you can see, the topmost item is denoted as the top. When you push something to the stack, it becomes the new top. When you pop something from the stack, you pop the current top and set the next top as top.next
![ex](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/stack1.PNG)

#### Push O(1)
Pushing a Node onto a stack will always be an O(1) operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.

#### Pop O(1)
Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.

#### Peek O(1)
When conducting a peek, you will only be inspecting the top Node of the stack.

## What is a Queue
Similar to a stack, a queue is a linear data structure. Unlike a stack, a queue deletes only the oldest added data.  


* **FIFO**:
First In First Out

This means that the first item in the queue will be the first item out of the queue.

* **LILO**:
Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

### Queue Visualization
![ex](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Queue.PNG)

#### Enqueue O(1)
When you add an item to a queue, you use the enqueue action. This is done with an O(1) operation in time because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

#### Dequeue O(1)
When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.

#### Peek O(1)
When conducting a peek, you will only be inspecting the front Node of the queue.

