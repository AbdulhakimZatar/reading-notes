# HTTP and REST

## Review, Research, and Discussion

**Define three related pieces of data in a possible application. An example for a store application might be Product, Category and Department. Describe the constraints and rules on each piece of data and how you would relate these pieces to each other. For example, each Product has a Category and belongs in a Department.**

* Track your Net Promoter Score
* Keep an updated record of all contact information
* Collect user experience data

Xero

We ask all of our users, "How likely are you to recommend our product to a friend or colleague (on a scale of 1 to 10)?" Then we use this data to calculate our Net Promoter Score, or the percentage of promoters (nines and 10s) minus the percentage of detractors (ones to sixes). We always follow up the question with a "Why?" and we get lots of really important insights from this simple question.

Whether you’re running a website or a brick-and-mortar, maintaining a database of your customers is one of the most important things you can do. A large part of our sales are generated by repeat customers when we reach out to them (instead of vice versa). 

We collect data that relates to how our customers use our hardware and our apps. First, this allows us to prioritize the features in a UI and create a better user experience. Second, we can use data to determine which functions are more popular. We then use this data to prioritize new feature rollouts or certain functions over others. Data is a great way to create better and more meaningful experiences.


**What is the advantage of an ORM, like Mongoose?**
* Productivity
* Application design
* Code Reuse
* Application Maintainability


**How does the repository pattern compare with an ORM?**
* Repositories deal with Domain/Business objects 
* ORM handles db objects.

**When making a repository/facade, what flexibility do you gain?**
Facades serve as "static proxies" to underlying classes in the service container, providing the benefit of a terse, expressive syntax while maintaining more testability and flexibility than traditional static methods.

**Name 3 cloud based NoSQL Databases**
* Couchbase.
* Amazon DynamoDB.
* MongoDB.


## Document the following Vocabulary Terms
**lifecycle**:the series of changes in the life of an organism including reproduction.


**collections**: collection is a class used to represent a set of similar data type items as a single unit.

**the “Repository” design pattern**:is a kind of container where data access logic is stored.

**mongoose middleware**:functions which are passed control during execution of asynchronous functions.

**Object Relation Mapping (ORM)**:programming technique for converting data between incompatible type systems using object-oriented programming languages.

## Preparation Materials

### HTTP
HTTP stands for Hypertext Transfer Protocol. It's a stateless, application-layer protocol for communicating between distributed systems, and is the foundation of the modern web.

#### HTTP Basics
HTTP allows for communication between a variety of hosts and clients, and supports a mixture of network configurations.

This makes HTTP a stateless protocol. The communication usually takes place over TCP/IP, but any reliable transport can be used. The default port for TCP/IP is 80, but other ports can also be used.

Communication between a host and a client occurs, via a request/response pair. The client initiates an HTTP request message, which is serviced through a HTTP response message in return. We will look at this fundamental message-pair in the next section.

![ex](https://cdn.tutsplus.com/net/authors/jeremymcpeak/http1-request-response.png)

#### URLs
At the heart of web communications is the request message, which are sent via Uniform Resource Locators (URLs). 
![ex](https://cdn.tutsplus.com/net/authors/jeremymcpeak/http1-url-structure.png)

#### Verbs  
URLs reveal the identity of the particular host with which we want to communicate, but the action that should be performed on the host is specified via HTTP verbs. 
* GET: fetch an existing resource. The URL contains all the necessary information the server needs to locate and return the resource.
* POST: create a new resource. POST requests usually carry a payload that specifies the data for the new resource.
* PUT: update an existing resource. The payload may contain the updated data for the resource.
* DELETE: delete an existing resource.

#### Status Codes
* 1xx: Informational Messages
* 2xx: Successful
* 3xx: Redirection
* 4xx: Client Error
* 5xx: Server Error

### REST
REST is acronym for REpresentational State Transfer. It is architectural style for distributed hypermedia systems and was first presented by Roy Fielding in 2000 in his famous dissertation.

#### Resource Methods
Important thing associated with REST is resource methods to be used to perform the desired transition. A large number of people wrongly relate resource methods to HTTP GET/PUT/POST/DELETE methods.

#### REST and HTTP are not same !!
because REST also intends to make the web (internet) more streamline and standard, he advocates using REST principles more strictly. And that’s from where people try to start comparing REST with web (HTTP).