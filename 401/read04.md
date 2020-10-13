# Advanced Mongo/Mongoose

## Review, Research, and Discussion
Why would a developer choose to make data models?
makes it easier to integrate high-level business processes with data rules, data structures, and the technical implementation of your physical data.

What purpose do CRUD operations serve?
are the four basic functions of persistent storage. Alternate words are sometimes used when defining the four basic functions of CRUD, such as retrieve instead of read, modify instead of update, or destroy instead of delete.

What kind of database is Postgres? What kind of database is MongoDB?
object-relational.
NoSQL database.

What is Mongoose and why do we need it?
an Object Data Modeling (ODM) library for MongoDB and Node. js.
It manages relationships between data, provides schema validation, and is used to translate between objects in code and the representation of those objects in MongoDB.


## Document the following Vocabulary Terms

database: a data structure that stores organized information.

data model: is an abstract model that organizes elements of data and standardizes how they relate to one another and to the properties of real-world entities.

CRUD: Four basic functions of persistent storage.

schema: its structure described in a formal language supported by the database management system.

sanitize: Provides a set of drush commands to assist in generating a database.sanitize.yml file containing all the queries for database sanitization.

Structured Query Language (SQL): used to communicate with a database.

Non SQL (NoSQL): database provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases.

MongoDB: cross-platform document-oriented database program. 

Mongoose: provides a straight-forward, schema-based solution to model your application data.

record: refers to a collection of fields about the same person/item/object.

document: type of nonrelational database that is designed to store and query data as JSON-like documents. 

Object Relation Mapping (ORM): programming technique for converting data between incompatible type systems using object-oriented programming languages.

## Preparation Materials

### The Repository Design Pattern
![img](https://cubettech.com/wp-content/uploads/2015/07/Reposiory-Design-Pattern.png)
To put it simply, Repository pattern is a kind of container where data access logic is stored. It hides the details of data access logic from business logic. In other words, we allow business logic to access the data object without having knowledge of underlying data access architecture.

The separation of data access from business logic have many benefits. Some of them are:

* Centralization of the data access logic makes code easier to maintain
* Business and data access logic can be tested separately
* Reduces duplication of code
* A lower chance for making programming errors

Repository design pattern is  fully stick onto interfaces. An interface acts like a contract which specify what an concrete class must implement. Let’s explore it a little bit. Suppose we have two data objects Uploader and Video, what are common set of operations that can be applied to these two data objects? In most situations we want to have the following operations:

* Get all records
* Get paginated set of records
* Create a new record
* Get record by it’s primary key
* Get record by some other attribute
* Update a record
* Delete a record

If we implement these operations for each object, you can imagine that the number of duplicate code in the entire application. For small application it doesn’t matter, but for larger applications it is a bad news.

#### Flexibility through Repositories
In order to separate our Controllers from the database in right manner, we are going to abstract that interaction into repositories. A repository is simply an interface between two things.

#### What do we need to build?
In order for our application to use Repositories, first we need to set things up.
We are going to need:

* UserRepository
* EloquentUserRepository
* A way to bind UserRepository and EloquentUserRepository

### Wrapping Up
Repositories allow you to create a flexible abstraction layer between your database and your Controller. Doing this enables you to separate those concerns and it prevents your Controllers being too tightly coupled with your Database.


### In Memory Database Testing
* No need for mocks: Your code is directly executed using the in-memory database, exactly the same as using your regular database.
* Faster development: Given that I don't need to build a mock for every operation and outcome but only test the query, I found the development process to be faster and more straightforward.
* More reliable tests: You're testing the actual code that will be executed on production, instead of some mock that might be incorrect, incomplete or outdated.
* Tests are easier to build: I'm not an expert in unit testing and the fact that I only need to seed the database and execute the code that I need to test made the whole process a lot easier to me.


* The in-memory database probably needs seeding
* More memory usage (dah)
* Tests take longer to run (depending on your hardware).

In conclusion, the in memory database turned out to be perfect to test applications where the logic is mainly handled through database operations and where the memory and execution time are not an issue.

### Let's start coding!

1- Setup & Install dependencies.

2- Write code to test.
Product schema and service

3- Configure jest

4- In-memory database handling
```js
// tests/db-handler.js

const mongoose = require('mongoose');
const { MongoMemoryServer } = require('mongodb-memory-server');

const mongod = new MongoMemoryServer();

/**
 * Connect to the in-memory database.
 */
module.exports.connect = async () => {
    const uri = await mongod.getConnectionString();

    const mongooseOpts = {
        useNewUrlParser: true,
        autoReconnect: true,
        reconnectTries: Number.MAX_VALUE,
        reconnectInterval: 1000
    };

    await mongoose.connect(uri, mongooseOpts);
}

/**
 * Drop database, close the connection and stop mongod.
 */
module.exports.closeDatabase = async () => {
    await mongoose.connection.dropDatabase();
    await mongoose.connection.close();
    await mongod.stop();
}

/**
 * Remove all the data for all db collections.
 */
module.exports.clearDatabase = async () => {
    const collections = mongoose.connection.collections;

    for (const key in collections) {
        const collection = collections[key];
        await collection.deleteMany();
    }
}
```

5- Write some tests
```js
// tests/product.test.js

const mongoose = require('mongoose');

const dbHandler = require('./db-handler');
const productService = require('../src/services/product');
const productModel = require('../src/models/product');

/**
 * Connect to a new in-memory database before running any tests.
 */
beforeAll(async () => await dbHandler.connect());

/**
 * Clear all test data after every test.
 */
afterEach(async () => await dbHandler.clearDatabase());

/**
 * Remove and close the db and server.
 */
afterAll(async () => await dbHandler.closeDatabase());

/**
 * Product test suite.
 */
describe('product ', () => {

    /**
     * Tests that a valid product can be created through the productService without throwing any errors.
     */
    it('can be created correctly', async () => {
        expect(async () => await productService.create(productComplete))
            .not
            .toThrow();
    });
});

/**
 * Complete product example.
 */
const productComplete = {
    name: 'iPhone 11',
    price: 699,
    description: 'A new dual‑camera system captures more of what you see and love. '
};
```
6- Try it out!