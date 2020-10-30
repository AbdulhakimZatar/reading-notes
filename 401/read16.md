# Event Driven Applications

## Review, Research, and Discussion
* Why is access control important?

Minimize the risk of unauthorized access to physical and logical systems.

* Describe an application that would need access control.

E-commerce, it need normal users and admin or provider to fill the website with products.

* What is a role used for?

It is used by the majority of enterprises with more than 500 employees, and can implement mandatory access control (MAC) or discretionary access control (DAC).

* Why is role based access control more scalable than discretionary or mandatory access control?

Essentially, RBAC assigns permissions to particular roles in an organization. Users are then assigned to that particular role. For example, an accountant in a company will be assigned to the Accountant role, gaining access to all the resources permitted for all accountants on the system. Similarly, a software engineer might be assigned to the developer role.

Roles differ from groups in that while users may belong to multiple groups, a user under RBAC may only be assigned a single role in an organization. Additionally, there is no way to provide individual users additional permissions over and above those available for their role. The accountant described above gets the same permissions as all other accountants, nothing more and nothing less.

## Document the following Vocabulary Terms
* **Authorization**: the function of specifying access rights/privileges to resources, which is related to information security and computer security in general and to access control in particular.
* **Role Based Access Control**: method of restricting network access based on the roles of individual users within an enterprise. 
* **Capabilities**: the ability to perform or achieve certain actions or outcomes.

## Preparation Materials

### Event Driven Programming
Event-Driven Programming is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision. In this article we’re going to go over how Event-Driven Programming works and how we can make the best use of it in our Node.js projects.

For the most recognizable example of Event-Driven Programming for people at any level of programming skill, we’ll turn to our old friend The Web Browser.

Every time you interact with a webpage through it’s user interface, an event is happening. When you click a button a click event is triggered. When you press a key a keydown event is triggered. These events have associated functions that, when triggered, are executed to make a change to the user interface in some way.

#### EventEmitter
Node.js natively provides us with a useful module called EventEmitter that allows us to get started incorporating Event-Driven Programming in our project right away. Of course, creating our own version of EventEmitter wouldn’t be much of a challange, and in fact there are several modules published on npm such as EventEmitter2 and EventEmitter3 which promise a faster performance than the native EventEmitter.

We access the EventEmitter class through the events module. Once imported we’ll need to create a new object from the class to start using it.

```js 
const EventEmitter = require('events').EventEmitter;
const myEventEmitter = new EventEmitter;
```

#### Removing Listeners
There will likely come a time when you want to remove an event listener from an event. This could be for performance reasons (the event is no longer needed) or to avoid memory leaks (if an event listener references an object that is no longer needed, it won’t be able to be garbage-collected. This can lead to a build up of unnecessary objects).

#### Object Oriented Programming + Event-Driven Programming
The last thing I want to touch on here is the combination of the Object Oriented and Event-driven programming paradigms. These two make for a very valuable combination in a wide variety of situations and I think it can be beneficial to understand and conceptualize why.