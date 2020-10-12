# Data Modeling & NoSQL Databases


## Review, Research, and Discussion

#### Name 3 advantages to Test Driven Development
1- Better program design and higher code quality.
2- Detailed project documentation.
3- TDD reduces the time required for project development.

#### In what case would you need to use beforeEach() or afterEach() in a test suite?
The difference is beforeEach()/afterEach() automatically run before and after each tests, which 1. removes the explicit calls from the tests themselves, and 2. invites inexperienced users to share state between tests.

#### What is one downside of Test Driven Development
Ideally a whole company or organisation needs to support the implementation of TDD in order for it to succeed.

#### What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?
Classes can’t be called without new, but functions intended as constructors can.
Classes can extend more types than constructors can .
Classes are also scoped.

#### Name a use case for a static method
Static methods are used to implement functions that belong to the class, but not to any particular object of it.

#### Write an example of a Higher Order function and describe the use case it solves
Below loops over an array and invokes a function on each item until it has reached the last item. The capability of taking a function that it can invoke is what makes it a higher-order function:
```js
function prefixWordWithUnderscore(word) {
  return `_${word}`
}

const words = ['coffee', 'apple', 'orange', 'phone', 'starbucks']
const prefixedWords = words.map(prefixWordWithUnderscore)

// result: ["_coffee", "_apple", "_orange", "_phone", "_starbucks"]
```


## Document the following Vocabulary Terms

functional programming: is a programming paradigm where programs are constructed by applying and composing functions.

pure function: is a function where the return value is only determined by its input values, without observable side effects.

higher-order function:  is a function that takes a function as an argument, or returns a function.

immutable state: designed to overcome the issues with immutability inherent within JavaScript, providing all the benefits of immutability with the performance your app requires.

object: are containers for named values called properties or methods.

object-oriented programming (OOP): s a computer programming model that organizes software design around data, or objects, rather than functions and logic. 

class: are a template for creating objects.

prototype: are the mechanism by which JavaScript objects inherit features from one another.

super: keyword is used to access and call functions on an object's parent.

inheritance: is an important concept in object oriented programming. In the classical inheritance, methods from base class get copied into derived class. 

constructor: method is a special method of a class for creating and initializing an object of that class.

instance: Instance properties must be defined inside of class methods.

context:object represents a JavaScript execution environment.

this: this keyword behaves a little differently in JavaScript compared to other languages.

Test Driven Development (TDD):  development technique where you must first write a test that fails before you write new functional code.

Jest: delightful JavaScript Testing Framework with a focus on simplicity.

Continuous Integration (CI): is the process of automating the build and testing of code every time a team member commits changes.


## Preparation Materials

### SQL vs NoSQL

- SQL databases are primarily called as Relational Databases (RDBMS); whereas NoSQL database are primarily called as non-relational or distributed database.

- SQL databases are table based databases whereas NoSQL databases are document based, key-value pairs, graph databases or wide-column stores. 

- SQL databases have predefined schema whereas NoSQL databases have dynamic schema for unstructured data.

- SQL databases are vertically scalable whereas the NoSQL databases are horizontally scalable. 

- For complex queries: SQL databases are good fit for the complex query intensive environment whereas NoSQL databases are not good fit for complex queries.

### noSQL Modeling Techniques
NoSQL databases are often compared by various non-functional criteria, such as scalability, performance, and consistency.

we should note that SQL and relational model in general were designed long time ago to interact with the end user.

#### General Notes on NoSQL Data Modeling
- NoSQL data modeling often starts from the application-specific queries as opposed to relational modeling

- NoSQL data modeling is typically driven by application-specific access patterns, i.e. the types of queries to be supported.

- NoSQL data modeling often requires a deeper understanding of data structures and algorithms than relational database modeling does. 

#### Conceptual Techniques
1- Denormalization

2- Aggregates

3- Application Side Joins

4- Atomic Aggregates

5- Enumerable Keys

6- Dimensionality Reduction

7- Index Table

8- Composite Key Index

9- Aggregation with Composite Keys

10- Inverted Search – Direct Aggregation

11- Tree Aggregation

12- Adjacency Lists

13- Materialized Paths

14- Nested Sets

15- Nested Documents Flattening: Numbered Field Names

16- Nested Documents Flattening: Proximity Queries

17- Batch Graph Processing
